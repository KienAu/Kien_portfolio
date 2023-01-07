<template>
  <nav class="navigation">
    <transition name="navigation__transition--is-fade">
      <ul class="navigation__list" v-if="isActive" :class="{'navigation__list--is-active': isActive}" >
        <li class="navigation__item display-mobile-only">
          <span class="navigation__logo">
            <Logo />
          </span>
        </li>
        <li class="navigation__item">
          <router-link class="navigation__link" to="/">
            <span class="navigation__text" @click="toggle(isActive)">Intro</span>
          </router-link>
        </li>
        <li class="navigation__item">
          <router-link class="navigation__link" to="/about">
            <span class="navigation__text">About</span>
          </router-link>
        </li>
        <li class="navigation__item">
          <router-link class="navigation__link" to="/portfolio">
            <span class="navigation__text">Project</span>
          </router-link>
        </li>
        <li class="navigation__item">
          <router-link class="navigation__link" to="/contact">
            <span class="navigation__text">Contact</span>
          </router-link>
        </li>
      </ul>
    </transition>

    <div class="navigation__hamburger display-mobile-only" :class="{'navigation__hamburger--is-active': isActive}" @click="isActive = !isActive">
      <div class="navigation__hamburger__line half start"></div>
      <div class="navigation__hamburger__line"></div>
      <div class="navigation__hamburger__line half end"></div>
    </div>
  </nav>
</template>

<script>
import Logo from "../assets/logo.svg";

export default {
  name: "Navigation",
  data() {
    return {
      isActive: false,
    };
  },

  mounted() {
    const mediaQueryList = window.matchMedia("(min-width: 768px)");
    if (mediaQueryList.matches) {
      this.isActive = true;
    } else {
      this.isActive = false;
    }
  },
  methods: {
    onResize() {
      if (window.innerWidth > 768) {
        this.isActive = true;
      } else {
        this.isActive = false;
      }
    },
  },

  created() {
    window.addEventListener("resize", this.onResize);
  },

  beforeDestroy() {
    window.removeEventListener("resize", this.onResize);
  },

  watch: {
    $route() {
      if (window.innerWidth > 768) {
        this.isActive = true;
      } else {
        this.isActive = false;
      }
    },
  },

  components: {
    Logo,
  },
};
</script>
