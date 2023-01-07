<template>
  <div class="contact">
    <div class="container page">
      <div class="contact__content">
        <h3 class="contact__title">Get in touch with me</h3>
        <p class="contact__text">
          If you have any questions, please feel free to drop me a line.<br>
          If you don't get an answer immediately, I might just be busy with my
          work or my personal life. I'll get back to you as soon as I can.<br>
          That's a promise!
        </p>
      </div>
      <div class="contact__content">
        <span class="contact__subtitle">FIND OLIVER ELSEWHERE</span>
        <ul class="contact__info__list">
          <li class="contact__info__item"><span class="contact__info__text">Telephone No.: 514 703-8268</span></li>
          <li class="contact__info__item"><span class="contact__info__text">Email: oliverau93@gmail.com</span></li>
        </ul>
        <div class="contact__social">
          <ul class="contact__social__list">
            <li class="contact__social__item">
              <a class="contact__social__link" href="https://www.instagram.com/kien_au/">
                <font-awesome-icon :icon="['fab', 'instagram']" size="lg" />
                <span class="contact__social__text">@Kien_Au</span>
              </a>
            </li>
            <li class="contact__social__item">
              <a class="contact__social__link" href="https://www.linkedin.com/in/oliver-au-48172b136/">
                <font-awesome-icon :icon="['fab', 'linkedin']" size="lg" />
                <span class="contact__social__text">Oliver Au</span>
              </a>
            </li>
            <li class="contact__social__item">
              <a class="contact__social__link" href="https://discordapp.com/users/220695825989238784">
                <font-awesome-icon :icon="['fab', 'discord']" size="md" />
                <span class="contact__social__text">@Kien#2331</span>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  metaInfo: {
    title: "Contact",
    htmlAttrs: {
      lang: "en",
      amp: true,
    },
  },
  name: "Contact",
};
</script>

