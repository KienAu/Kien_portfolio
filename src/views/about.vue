<template>
  <section class="about">
    <AboutMe />
    <AboutSkill />
  </section>
</template>

<script>
import AboutSkill from '@/components/about-skills.vue';
import AboutMe from '@/components/about-me.vue'

export default {
  metaInfo: {
    title: "About",
    htmlAttrs: {
      lang: "en",
      amp: true,
    },
  },
  name: "About",
  components: {
    AboutSkill,
    AboutMe
  },
  computed: {
    calculateAge: function () {
      let currentDate = new Date();
      let birthDate = new Date("1993/10/16");
      let difference = currentDate - birthDate;
      let age = Math.floor(difference / 31557600000);
      return age;
    },
  },
};
</script>
