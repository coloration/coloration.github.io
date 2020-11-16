<script setup lang="ts">

const toc = ref<HTMLElement | null>(null)

onMounted(() => {
  const tocDom = globalThis.document.querySelector('.table-of-contents')
  if (!toc.value || !tocDom) return
  toc.value.appendChild(tocDom)
})
</script>
<template>
  <div class="mk md:flex md:justify-between">
    <div class="relative my-12 md:my-0 md:w-64 md:mr-12 lg:mr-20 md:flex-shrink-0">
      <div ref="toc" />
    </div>
    <div class="max-w-3xl mx-auto" data-aos="fade-up">
      <slot />
    </div>
  </div>
</template>
