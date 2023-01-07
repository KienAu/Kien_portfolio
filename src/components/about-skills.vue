<template>
  <div class="container page">
    <tabs>
      <tab class="about__soft-lang" name="Software &amp; Language" id="Soft-Lang" :selected="true">
        <div class="about__flex">
          <div class="about__image-container">
            <img class="about__soft-lang__image" src="../assets/skill-1.jpg" />
          </div>
          <span class="about__title about__soft-lang__title">I mainly work with:</span>
        </div>
        <div class="about__flex about__soft-lang__content">
          <ul class="about__soft-lang__list">
            <li class="about__soft-lang__item" v-for="item in splitArray.odds" :key="item.skill">
              <div class="about__soft-lang__progress-line">
                <span class="about__soft-lang__skill">{{ item.skill }} </span>
                <span class="about__soft-lang__progress-percentage">{{ item.progress }} </span>
              </div>
            </li>
          </ul>
          <ul class="about__soft-lang__list">
            <li class="about__soft-lang__item" v-for="item in splitArray.evens" :key="item.skill">
              <div class="about__soft-lang__progress-line">
                <span class="about__soft-lang__skill">{{ item.skill }} </span>
                <span class="about__soft-lang__progress-percentage">{{ item.progress }} </span>
              </div>
            </li>
          </ul>
        </div>
      </tab>

      <tab class="about__expertise" name="Expertise" id="Expertise">
        <div class="about__flex about__expertise__content">
          <span class="about__title about__expertise__title">What I do:</span>
          <ul class="about__expertise__list">
            <li class="about__expertise__item" v-for="item in splitDirection.odds" :key="item.title">
              <span class="about__expertise__job-skill">{{ item.title }}</span>
            </li>
          </ul>
          <ul class="about__expertise__list">
            <li class="about__expertise__item" v-for="item in splitDirection.evens" :key="item.title">
              <span class="about__expertise__job-skill">{{ item.title }}</span>
            </li>
          </ul>
        </div>
        <div class="about__flex">
          <div class="about__image-container">
            <img class="about__expertise__image" src="../assets/skill-2.jpg" />
          </div>
        </div>
      </tab>
    </tabs>
  </div>
</template>

<script>
import tab from "@/components/tab.vue";
import tabs from "@/components/tabs.vue";

export default {
  name: "Skill",
  components: {
    tab,
    tabs,
  },
  data() {
    return {
      mainSkills: [
        {
          skill: "HTML",
          progress: "90%",
        },
        {
          skill: "CSS | SASS",
          progress: "90%",
        },
        {
          skill: "JS | JQUERY",
          progress: "70%",
        },
        {
          skill: "Vue.js",
          progress: "50%",
        },
        {
          skill: "Adobe Photoshop",
          progress: "80%",
        },
        {
          skill: "Adobe Illustrator",
          progress: "80%",
        },
        {
          skill: "Adobe XD",
          progress: "85%",
        },
        {
          skill: "Boostrap",
          progress: "90%",
        },
      ],
      Direction: [
        {
          title: "UI/UX Design",
        },
        {
          title: "Illustration",
        },
        {
          title: "Creative Web Design",
        },
        {
          title: "Front-end Development",
        },
        {
          title: "Photo Retouch",
        },
        {
          title: "Graphic Design",
        },
        {
          title: "Creative Code",
        },
        {
          title: "Strategy",
        },
      ],
    };
  },
  computed: {
    splitArray() {
      const [evens, odds] = this.mainSkills.reduce(
        (res, item, i) => {
          res[i % 2].push(item);
          return res;
        },
        [[], []]
      );
      return { evens, odds };
    },
    splitDirection() {
      const [evens, odds] = this.Direction.reduce(
        (res, item, i) => {
          res[i % 2].push(item);
          return res;
        },
        [[], []]
      );
      return { evens, odds };
    },
  },
};
</script>
