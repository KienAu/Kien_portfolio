<template>
  <div id="website">
    <navigation />
    <main class="view">
      <transition name="fade">
        <router-view />
      </transition>
    </main>
    <SocialMedia />
  </div>
</template>

<script>
import Navigation from "@/components/navigation.vue";
import SocialMedia from "@/components/social-media.vue";

export default {
  metaInfo: {
    // if no subcomponents specify a metaInfo.title, this title will be used
    title: "Oliver 'Kien' Au Portfolio",
    // all titles will be injected into this template
    titleTemplate: "Kien E-portfolio | %s ",
  },
  components: {
    Navigation,
    SocialMedia,
  },
};
</script>

<style lang="scss">
  @import "../src/sass/main.scss";
</style>