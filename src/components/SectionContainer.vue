<template>
  <section v-bind="$attrs" class="section-container">
    <slot />
  </section>
</template>
<style>
.section-container {
  max-width: 1128px;
  @apply px-6 mx-auto;
}
</style>
