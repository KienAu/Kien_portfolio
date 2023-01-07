
<template>
  <div class="profile__info">
    <div class="profile__transition">
      <transition name="fade">
        <span v-if="show" style="transition-delay: 0.6s" class="profile__intro">
          Hi,
        </span>
      </transition>
    </div>

    <div class="profile__transition">
      <transition name="fade">
        <span class="profile__intro" v-if="show" style="transition-delay: 0.8s">My name is</span>
      </transition>
    </div>

    <div class="profile__transition">
      <transition name="fade">
        <h1 v-if="show" class="profile__title" style="transition-delay: 1.2s">Oliver Au</h1>
      </transition>
    </div>

    <transition name="fade">
      <span class="profile__jobtitle" style="transition-delay: 1.6s" v-if="show">
        <transition name="fade" mode="out-in">
          <span class="profile__jobtitle-text" :key="Job">{{ Job }}</span>
        </transition>
      </span>
    </transition>
  </div>
</template>

<script>
var i = 0;

export default {
  name: "ProfileInfo",

  data: function () {
    return {
      jobTitle: [
        "Web Designer",
        "Front-end Developer",
        "UI & UX Designer",
        "Graphic Designer",
        "Freelancer"
      ],
      Job: "",
      show: false,
    };
  },

  methods: {
    updateJob: function () {
      this.Job = this.jobTitle[i++];
      if (i == this.jobTitle.length) {
        i = 0;
      }
    },
  },
  
  mounted: function () {
    this.updateJob();
    setInterval(this.updateJob, 2000);
    this.show = true;
  },
}
</script>