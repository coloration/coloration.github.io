<script lang="ts" setup>import type { PropType } from 'vue'

defineProps({
  src: {
    type: String as PropType<string>,
    required: true,
  },
})
</script>
<template>
  <div class="w-18 h-18 features-tiles-item-image">
    <img class="w-full h-full block" :src="src" alt="">
  </div>
</template>
<style>
.features-tiles-item-image {
  display: inline-flex;
  background-repeat: no-repeat;
  background-size: 100%;
  border-radius: 50%;
  background-color: #6448FB;
  background-image:
    url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNzIiIGhlaWdodD0iNzIiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGRlZnM+PGxpbmVhckdyYWRpZW50IHgxPSI1MCUiIHkxPSIxMDAlIiB4Mj0iNTAlIiB5Mj0iMCUiIGlkPSJhIj48c3RvcCBzdG9wLWNvbG9yPSIjRkY4OEU0IiBzdG9wLW9wYWNpdHk9Ii40OCIgb2Zmc2V0PSIwJSIvPjxzdG9wIHN0b3AtY29sb3I9IiNGRjg4RTQiIHN0b3Atb3BhY2l0eT0iMCIgb2Zmc2V0PSIxMDAlIi8+PC9saW5lYXJHcmFkaWVudD48L2RlZnM+PHBhdGggZD0iTTU0IDkwYzE5Ljg4MiAwIDM2LTE2LjExOCAzNi0zNlM3My44ODIgMTggNTQgMThzMTEgMTYtMzYgMzYgMTYuMTE4IDM2IDM2IDM2eiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTQpIiBmaWxsPSJ1cmwoI2EpIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiLz48L3N2Zz4=),
    linear-gradient(#8E79FC, #6448FB);
}
</style>
