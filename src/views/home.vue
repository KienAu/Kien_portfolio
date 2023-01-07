<template>
  <section class="profile">
    <div class="container page">
      <profileInfo />
      <transition name="fade">
        <profileImg />
      </transition>
    </div>
  </section>
</template>

<script>
import profileImg from "@/components/profile-img.vue";
import profileInfo from "@/components/profile-info.vue";

export default {
  name: "Home",
  metaInfo: {
    title: "Intro",
    htmlAttrs: {
      lang: "en",
      amp: true,
    },
  },
  components: {
    profileImg,
    profileInfo
  },
};
</script>

