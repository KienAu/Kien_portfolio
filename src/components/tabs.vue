
<template>
  <div class="about__skill">
    <div class="tabs">
      <ul class="tabs__list">
        <li v-for="tab in tabs" :key="tab" :class="{ 'tabs__item--is-active': tab.isActive }" class="tabs__item">
          <a class="tabs__link" :href="tab.href" @click="selectTab(tab)" >{{ tab.name }}</a>
        </li>
      </ul>
    </div>
    <div class="tabs__details">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tabs: [],
    };
  },
  created() {
    this.tabs = this.$children;
  },
  methods: {
    selectTab(selectedTab) {
      this.tabs.forEach((tab) => {
        tab.isActive = tab.name == selectedTab.name;
      });
    },
  },
};
</script>