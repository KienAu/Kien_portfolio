<template>
  <div class="social-media">
    <div class="social-media__logo">
      <router-link to="/" class="social-media__logo__link">
        <Logo />
      </router-link>
    </div>

    <div class="social-media__container">
      <p class="social-media__text">| Follow my social media</p>
      <ul class="social-media__list">
        <li class="social-media__item">
          <a class="social-media__link" href="https://www.instagram.com/kien_au/">
            <font-awesome-icon :icon="['fab', 'instagram']" size="lg" />
          </a>
        </li>
        <li class="social-media__item">
          <a class="social-media__link" href="https://www.linkedin.com/in/oliver-au-48172b136/">
            <font-awesome-icon :icon="['fab', 'linkedin']" size="lg" />
          </a>
        </li>
        <li class="social-media__item">
          <a class="social-media__link" href="https://discordapp.com/users/220695825989238784">
            <font-awesome-icon :icon="['fab', 'discord']" size="md" />
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Logo from "../assets/logo.svg";

export default {
  name: "SocialMedia",
  components: {
    Logo,
  },
};
</script>
