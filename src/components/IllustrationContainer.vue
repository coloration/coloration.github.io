<script lang="ts" setup>
import type { PropType } from 'vue'

defineProps({
  src: {
    type: String as PropType<string>,
  },
  height: {
    type: Number as PropType<number>,
  },
})

</script>
<template>
  <section v-bind="$attrs" class="illustration-container">
    <div v-if="src" class="illustration" :style="{ backgroundImage: `url(${src})`, height: height ?? '100%' }" />
    <div class="relative z-10">
      <slot />
    </div>
  </section>
</template>
<style>
.illustration-container {
  @apply relative;
}

.illustration {
    position: absolute;
    width: 100%;
    max-width: 100%;
    background-repeat: no-repeat;
    background-size: auto;
    left: 50%;
    top: 0;
    background-position: center top;
    transform: translate(-50%);
}
</style>
