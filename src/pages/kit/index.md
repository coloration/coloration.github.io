# @coloration/kit

- 项目地址Github: <https://github.com/coloration/kit>

<!-- more -->

[[toc]]


<p style="display: flex;">
<img src="https://img.shields.io/npm/v/@coloration/kit.svg" alt="version">
<img src="https://img.shields.io/npm/l/@coloration/kit.svg" alt="lic">
<img src="https://img.shields.io/npm/dm/@coloration/kit.svg" alt="Download">
</p>

## Start Up

### Install

``` bash
$ npm i @coloration/kit -S
```

## Operator

### curry 


柯里化一个函数, 将参数缓存起来, 返回一个新的函数.只接受剩下的参数. 如果再次传入的参数不足,则继续进行柯里化.


``` js
function add (a, b, c) { return a + b + c }

const add2 = curry(add, 2)
add2(3, 5) /* => 10 */
const add5 = add2(3)
add5(7) /* => 12 */

```

Note: 也是为了配合这个特性, `kit` 中所有的函数的配置函数都靠前, 数据参数都靠后(与 ramda 相同, 与lodash不同). 这符合函数式编程的习惯. 

``` js
function toTree(options, data) {/* code */}

const projectTreeFormatter = curry(toTree, treeOptions)

projectTreeFormatter([/* data array */])
```

### equal 

判断两值相等, 如果没有指定判断函数则使用 `Object.is` 判断.

``` js
equal(undefined, 5, 6) /* => false */

const customEqual = curry((a, b) => a.id === b.id)

customEqual({ id: 12, name: 'a' }, { id: 12, name: 'b' }) /* => true */
```

### is


### not

### deepEqual

### identity

返回值本身, 可用于过滤

``` js
identity('a') /* => 'a' */

['a', undefined, 3, null, [], 0].filter(identity)
/* => ['a', 3, []] */
```

### noop 

空函数, 一般用于不得不传函数,又没必要执行的地方.视情况而定

```js
fetchSome().then(/*  */).catch(noop)
```

### no

永远返回 `false`

### isDefind

```ts
isDefind(undefined) // => false
isDefind(null) // false

// other => true
```

### isObject

### isPlainObject

### isString

### isNumber

### isSymbol

### isBoolean

### isFunction

### isRegExp

### isPromise

### isPrimitive

### isIE

### copy

### clone

## Array

### toArray

transform any to array

``` ts
toArray<string>('1', '2') // => ['1', '2']
toArray<number>([5, 6]) // => [5, 6] new instance
toArray<{ id: number }[]>({ id: 1 }) // => [{ id: 1 }]
```

### arrayAdd

数组的条件添加，默认使用 `Object.is` 判断。如果相同则不添加。可以自定义添加条件。不修改
原数组，返回新数组实例。

``` ts
const arrUniAdd = curry(arrayAdd, undefined)

arrUniAdd([1, 2, 3, 4], [3, 4, 5, 6])
// => [1, 2, 3, 4, 5, 6]

arrUniAdd([1, 2, 3, 4], 0)
// => [1, 2, 3, 4, 0]

const businessUniAdd = curry(
  arrayAdd, 
  (a, b) => a.category === b.category && a.id !== b.id
)

businessUniAdd(
  [
    { category: 12, id: 4, name: 'black' }, 
    { category: 12, id: 5, name: 'pink' }
  ],
  [
    { category: 12, id: 6, name: 'green' },
    { category: 10, id: 90, name: 'apple' },
    { category: 12, id: 4, name: 'black' },
  ]
)

// => [
//  { category: 12, id: 4, name: 'black' }, 
//  { category: 12, id: 5, name: 'pink' },
//  { category: 12, id: 6, name: 'green' },
// ],
```

### arrayIncludes

same as `arrayAdd`. return boolean

### arrayRemove 

same as `arrayAdd`. return a new array instance

### arrayRepeat 

``` ts
arrayRepeat(5) // => [0, 1, 2, 3, 4]
arrayRepeat(3, 's') // => ['s', 's', 's']
arrayRepeat(3, (_, i) => i * i) // => [0, 1, 4]
```

### arrayPick

``` ts
const arr = [
  { name: 'Misha', value: 1 },
  { name: 'Huffer', value: 2 }
  { name: 'Leokk', value: 3 }
]

arrayPick('value', arr) // => [1, 2, 3]

const pickArrayName = curry(arrayPick, 'name')

pickArrayName(arr) // => ['Misha', 'Huffer', 'Leokk']
pickArrayName([1, 2]) // => [undefind, undefined]
```

### arraySlice

``` ts
const arr = [0, 1, 2]

arraySlice(arr, 0, 2) // => [0, 1]
arraySlice(arr, 0, 4) // => [0, 1, 2, 0]
arraySlice(arr, 1, 4) // => [1, 2, 0]
arraySlice(arr, -1, 7) // => [2, 0, 1, 2, 0, 1, 2, 0]
arraySlice(arr, -1, -5) // => []
```


## Object

### objectHas

### objectGet

### objectGetDefaultNull 

curry from 'objectGet'

### reverseEntries

### reverseKeyValue

### objectToQuery

### queryToObject

### toTree

### flattenTree


### findTreeParent

### findTreeParentFromList


## Function

## Number

### formatNumber 

### formatNumberToThousand

curry from `formatNumber`

### FormatNumberEnum

### softBind

## String

### stringLength

```ts
stringLength("董存瑞")) // => 3
stringLength("𝄞")) // => 1
stringLength("𝌆12")) // => 3
stringLength("im dongcunrui 大队长𝌆")) // => 18
```

### stringByteLength

``` ts
stringByteLength("董存瑞")) // => 6
stringByteLength("𝄞")) // => 3
stringByteLength("𝌆12")) // => 5
stringByteLength("im dongcunrui 大队长𝌆")) // => 23
```

### transformLetter

- `map`: 转换用对照字典
- `flag`: 替换时正则所遵守的规则. 默认`g`

``` ts
const ZH_CH_LOCALE = {
  'confirm': '确认',
  'delete': '删除'
}

const translateENToCH = curry(transformLetter, { map: ZH_CH_LOCALE })

translateENToCH('confirm delete?') // => '确认 删除?'
translateENToCH('confirmConfirm delete?') // => '确认Confirm 删除?'
translateENToCH('confirm delete?') // => '确认 删除?'
translateENToCH('confirm deletedelete?') // => '确认 删除删除?'

const translateENToCH = curry(transformLetter, { map: ZH_CH_LOCALE, flag: 'ig' })

translateENToCH('confirmConfirm delete?') // => '确认确认 删除?'

```

### transformToHalfSymbol

curry from `transformLetter`

### transformToFullSymbol

curry from `transformLetter`

## Math

### a

``` ts
a(3, 2)  // 6
a(5, 2)  // 20
```

### c

``` ts
c(3, 2)  // 3
c(5, 2)  // 10
```

### aPick

暂未添加

``` ts
aPick([1, 2, 3, 4, 5], 2)
// => [
//   [1, 2], [1, 3], [1, 4], [1, 5], [2, 3],
//   [2, 1], [3, 1], [4, 1], [5, 1], [3, 2],
//   [2, 4], [2, 5], [3, 4], [3, 4], [4, 5]  
//   [4, 2], [5, 2], [4, 3], [4, 3], [5, 4]  
// ]
```

### cPick

``` ts
cPick([1, 2, 3, 4, 5], 2)
// => [
//   [1, 2], [1, 3], [1, 4], [1, 5], [2, 3],
//   [2, 4], [2, 5], [3, 4], [3, 4], [4, 5]  
// ]
```

## Process

### microDelay

``` ts

let execTimes = 0
const microDelayFunc = microDelay(() => execTimes++)

microDelayFunc()
microDelayFunc()
microDelayFunc()

// execTimes => 0

Promise.resolve(() => {
  // execTimes => 1
})

setTimeout(() => {
  // execTimes => 0 (!)
}, 0)
```

### macroDelay

``` ts

let execTimes = 0
const macroDelayFunc = macroDelay(() => execTimes++)

macroDelayFunc()
macroDelayFunc()
macroDelayFunc()

// execTimes => 0

Promise.resolve(() => {
  // execTimes => 1
})

setTimeout(() => {
  // execTimes => 1 (!)
}, 0)
```

### delay

``` ts
```

### debounce

``` ts
```

### throttle

``` ts
```

## DOM

### copyToClipBoard

```js
copyToClipBoard('我很帅!')
.then(() => {
  // copy success
})
.catch(e => {
  // copy failure
})
```

### download

### downloadAsFile

### downloadAsCsv

### downloadDataurl

### getOffset

- `left`: 距离指定跟元素的左边距，累加 `offsetLeft`
- `top`: 距离指定跟元素的左边距，累加 `offsetTop`
- `width`: 元素自身 `offsetWidth`
- `height`: 元素自身 `offsetHeight`

``` ts
getOffset(document.body, buttonDom)

// => { left: 120, top: 500, width: 120, height: 30 }
```

### getOffsetFromBody 

curry from `getOffset`

``` ts
export const getOffsetFromBody = curry(getOffset, document.body)
```


## Const

export some const 

- `CHILDREN = 'children'`
- `CHILD = 'child'`
- `PARENT = 'parent'`
- `ID = 'id'`
- `PID = 'pid'`

