<template>
  <IllustrationContainer src="/images/illustration-section-01.svg" style="height: 778px;" class="pt-20">
    <section class="relative">
      <div class="relative max-w-6xl mx-auto px-4 sm:px-6">
        <div class="pt-32 pb-12 md:pt-40 md:pb-20">
          <ArticleHelper>
            <router-view />
          </ArticleHelper>
        </div>
      </div>
    </section>
  </IllustrationContainer>
</template>
