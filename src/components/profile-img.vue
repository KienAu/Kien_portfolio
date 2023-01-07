<template>
  <div class="profile__picture">
    <picture>
      <source
        media="(min-width: 1025px)"
        srcset="../assets/profile-pic-drawing.png"
      />
      <source
        media="(min-width: 0)"
        srcset="../assets/profile-pic-drawing_mobile.png"
      />
      <img class="profile__image" src="" alt="Oliver Au" />
    </picture>
  </div>
</template>

<script>
export default {
  name: "ProfileImage",
};
</script>
