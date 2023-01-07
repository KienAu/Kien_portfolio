<template>
  <div class="portfolio">
    <div class="container page">
      <div class="portfolio__wrapper">
        <h3 class="portfolio__title">My Projects &amp; Works</h3>
        <carousel />
      </div>
    </div>
  </div>
</template>

<script>
import Carousel from "@/components/carousel.vue";

export default {
  metaInfo: {
    title: "Portfolio",
    htmlAttrs: {
      lang: "en",
      amp: true,
    },
  },
  components: {
    Carousel,
  },

  name: "portfolio",
};
</script>