<template>
  <div class="container page">
    <div class="about__text">
      <span class="about__subtitle"
        >{{ calculateAge }} | MTL | WEB DESIGNER &amp; FRONT-END DEV</span
      >
      <p class="about__description">
        My name is Oliver, and I'm a Web Designer &amp; Front-end Developer. I have
        a keen interest in Web Dev and UI Animation. Currently working with
        Salefloors. Previous Graphic &amp; Web design student at John Abbott
        College. My job is to provide a professional website with a good cause
        and making solutions for my clients.
      </p>
    </div>
    <div class="about__picture-display">
      <div class="about__image-container">
        <img class="about__image" src="../assets/about_profile.jpg" />
      </div>
      <h3 class="about__title">
        About me &amp;
        <br />My future plans
      </h3>
    </div>
  </div>
</template>

<script>
export default {
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
