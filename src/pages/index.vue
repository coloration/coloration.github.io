<template>
  <IllustrationContainer src="/images/illustration-section-01.svg" style="height: 778px;" class="pt-20">
    <SectionContainer class="pt-30 pb-80">
      <h1 class="font-bold text-5xl mb-16 text-gray-800">
        Coloration
      </h1>
      <Paragraph class="mb-8 px-2 text-2xl">
        你也许能找到挺不错的开发工具
      </Paragraph>
      <p class="px-2 text-xl text-gray-400">
        轻松开发，早点回家
      </p>
    </SectionContainer>
  </IllustrationContainer>
  <SectionContainer class="text-center mb-20">
    <h2 class="font-semibold text-2xl mb-4">
      可使用的开源项目
    </h2>
    <paragraph>点击项目链接，你可以通过npm安装，也可以克隆到本地进行二次开发。或者提交PR完善我们共同的工具链</paragraph>
  </SectionContainer>
  <SectionContainer class="flex flex-wrap items-center">
    <div class="w-full order-1 md:w-1/2 md:order-none pb-20">
      <h3 class="text-2xl font-semibold mb-4 text-gray-700 hover:underline">
        <router-link to="/asker">
          @coloration/asker
        </router-link>
      </h3>
      <Paragraph>
        一个简单的，功能丰富的客户端HTTP工具，支持TS。大小只有4K
      </Paragraph>
    </div>
    <img class="w-full md:w-1/2" src="/images/features-split-top-01.png" alt="">
  </SectionContainer>
  <IllustrationContainer src="/images/illustration-section-03.svg">
    <SectionContainer class="flex flex-wrap items-center">
      <img class="w-full md:w-1/2" src="/images/features-split-top-02.png" alt="">
      <div class="w-full md:w-1/2 pb-20">
        <h3 class="text-2xl font-semibold mb-4 text-gray-700 hover:underline">
          <router-link to="/kit">
            @coloration/kit
          </router-link>
        </h3>
        <Paragraph>
          工具函数仓库，可以作为 lodash, ramda之外的补充
        </Paragraph>
      </div>
    </SectionContainer>
  </IllustrationContainer>
  <SectionContainer class="flex flex-wrap items-center">
    <div class="w-full order-1 md:w-1/2 md:order-none pb-20">
      <h3 class="text-2xl font-semibold mb-4 text-gray-700 hover:underline">
        <a href="//coloration.github.io/island">
          @Coloration/island
        </a>
      </h3>
      <Paragraph class="mb-2">
        Vue UI 组件库，集成Storybook开发环境, 方便二次开发
      </Paragraph>
      <Paragraph>a Vue UI component library with Storybook. Easy to develop</Paragraph>
    </div>
    <img class="w-full md:w-1/2" src="/images/features-split-top-03.png" alt="">
  </SectionContainer>
  <IllustrationContainer src="/images/illustration-section-05.svg" class="pt-20">
    <SectionContainer class="text-center mb-20">
      <h2 class="font-semibold text-2xl mb-4">
        更多有趣项目
      </h2>
      <Paragraph class="mb-20">
        如果你对此以下方面感兴趣，我可以为你提供更多的付费服务。或者你可以为我提供一个更好的工作机会。
      </Paragraph>

      <div class="flex flex-wrap gap-16  md:gap-0">
        <div class="w-full md:w-1/3 flex flex-col items-center w-full">
          <IconImage src="/images/feature-tile-icon-06.svg" />
          <h4 class="text-xl mt-10 mb-6 font-semibold cursor-pointer hover:underline">
            <a target="_blank" href="//fs.trans.pet">Finger Style</a>
          </h4>
          <Paragraph>乐谱渲染与播放，帮助新手快速学习吉他</Paragraph>
        </div>
        <div class="w-full md:w-1/3 flex flex-col items-center w-full">
          <IconImage src="/images/feature-tile-icon-04.svg" />

          <h4 class="text-xl mt-10 mb-6 font-semibold cursor-not-allowed  hover:underline">
            Ocean
          </h4>
          <Paragraph>解放双手，不做前端 DEVELOPING</Paragraph>
        </div>
        <div class="w-full md:w-1/3 flex flex-col items-center w-full">
          <IconImage src="/images/feature-tile-icon-05.svg" />

          <h4 class="text-xl mt-10 mb-6 font-semibold hover:underline">
            <a target="_blank" href="//binyu.me">Blog</a>
          </h4>
          <Paragraph>About Me</Paragraph>
        </div>
      </div>
    </SectionContainer>
  </IllustrationContainer>
  <IllustrationContainer src="/images/illustration-section-10.svg" class="mt-80 pb-80">
    <SectionContainer class="text-center">
      <h2 class="font-semibold text-2xl mb-4">
        获取更多帮助
      </h2>
      <Paragraph class="mb-20">
        如果你对此以下方面感兴趣，我可以为你提供更多的付费服务。或者你可以为我提供一个更好的工作机会。
      </Paragraph>

      <div class="flex flex-wrap gap-16 md:gap-0">
        <div class="w-full md:w-1/3 flex flex-col items-center w-full">
          <IconImage src="/images/feature-tile-icon-01.svg" />
          <h4 class="text-xl mt-10 mb-6 font-semibold">
            企业落地页
          </h4>
          <Paragraph>定制各种风格的企业黄页</Paragraph>
        </div>
        <div class="w-full md:w-1/3 flex flex-col items-center w-full">
          <IconImage src="/images/feature-tile-icon-02.svg" />
          <h4 class="text-xl mt-10 mb-6 font-semibold">
            可视化应用
          </h4>
          <Paragraph>可视化图表，大屏解决方案</Paragraph>
        </div>
        <div class="w-full md:w-1/3 flex flex-col items-center w-full">
          <IconImage src="/images/feature-tile-icon-03.svg" />

          <h4 class="text-xl mt-10 mb-6 font-semibold">
            技术咨询
          </h4>
          <Paragraph>提供或调研业界成熟解决方案</Paragraph>
        </div>
      </div>
    </SectionContainer>
  </IllustrationContainer>

  <SectionContainer class="py-20">
    <h4 class="text-2xl font-semibold text-gray-600 mb-6">
      联系我
    </h4>
    <Paragraph>406279919@qq.com</Paragraph>
  </SectionContainer>
  <div />
</template>

<script lang="ts" setup>
import IllustrationContainer from '../components/IllustrationContainer.vue'
</script>
<route lang="yaml">
meta:
  layout: home
</route>
