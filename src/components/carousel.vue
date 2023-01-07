<template>
  <div class="carousel">

    <div class="carousel__view carousel__view--is-big">
      <div class="carousel__nav display-mobile-only">
        <button class="carousel__button" @click="handleSlideChange(-1)">prev</button>
        <button class="carousel__button" @click="handleSlideChange(1)">next</button>
      </div> 
      
      <transition name="fade">
        <div
          class="carousel__progress-indicator display-mobile-only"
          :data-slides-count="'0' + slides.length"
          v-if="show"
        >
          <span
            v-for="(slide, index) of slides"
            :key="index"
            :class="
              index === currentSlide
                ? 'carousel__progress-indicator__bar carousel__progress-indicator__bar--is-active'
                : 'carousel__progress-indicator__bar'
            "
            v-on:click="select(index)"
          ></span>
        </div>
      </transition>
      <transition-group
        name="carousel__image"
        class="carousel__slider"
        tag="div"
        mode="in-out"
      >
        <img
          v-for="(slide, index) of slides"
          :key="index"
          class="carousel__image"
          :src="require('../assets/' + slide.img1)"
          v-show="index === currentSlide"
          :class="{'carousel__image--is-active': index === currentSlide}"
        />
      </transition-group>
      <div
        v-for="(slide, index) of slides"
        :key="index"
        v-show="currentSlide === index"
        class="carousel__text-slider"
      >
        <transition name="fade">
          <span v-if="show" class="carousel__categories">{{ slide.genre }}</span>
        </transition>
        <transition name="fade">
          <h2 v-if="show" class="carousel__subtitle">
            {{ slide.title }}
          </h2>
        </transition>
      </div>
    </div>

    <div class="carousel__view carousel__view--is-small">
      <a
        v-for="(slide, index) of slides"
        :key="index"
        :href="slide.link"
        class="carousel__link"
        v-show="index === currentSlide"
        >View Site</a
      >
      <transition-group
        name="carousel__image"
        class="carousel__slider"
        tag="div"
        mode="in-out"
      >
        <img
          v-for="(slide, index) of slides"
          :key="index"
          :src="require('../assets/' + slide.img2)"
          class="carousel__image"
          v-show="index === currentSlide"
          :class="{'carousel__image--is-active': index === currentSlide}"
        />
      </transition-group>   
      <div class="carousel__nav display-desktop-only">
        <button class="carousel__button" @click="handleSlideChange(1)">next</button>
        <button class="carousel__button" @click="handleSlideChange(-1)">prev</button>
      </div> 
      
      <transition name="fade">
        <div
          class="carousel__progress-indicator display-desktop-only display-desktop-only--is-flex"
          :data-slides-count="'0' + slides.length"
          v-if="show"
        >
          <span
            v-for="(slide, index) of slides"
            :key="index"
            :class="
              index === currentSlide
                ? 'carousel__progress-indicator__bar carousel__progress-indicator__bar--is-active'
                : 'carousel__progress-indicator__bar'
            "
            v-on:click="select(index)"
          ></span>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentSlide: 0,
      slides: [
        {
          id: 1,
          genre: "website",
          title: "Akido",
          img1: "akido_img.jpg",
          img2: "akido_img-2.jpg",
          link: "http://kienau.ca/pages/portfolio/Akido/index.html",
        },
        {
          id: 2,
          genre: "website",
          title: "Spa Dahlia",
          img1: "dahlia.jpg",
          img2: "dahlia2.jpg",
          link: "http://www.spadahlia.com/",
        },
        {
          id: 3,
          genre: "Website",
          title: "Sei",
          img1: "sei.jpg",
          img2: "sei2.jpg",
          link: "http://kienau.ca/pages/portfolio/sei/index.html",
        },
      ],
      show: false,
      loaded: false,
    };
  },
  computed: {
    nextSlide() {
      return this.currentSlide + 1 >= this.slides.length
        ? 0
        : this.currentSlide + 1;
    },
  },
  mounted: function () {
    this.show = true;
    this.loaded = true;
  },
  methods: {
    select: function (index) {
      console.log(index);
      this.currentSlide = index;
    },

    handleSlideChange(val) {
      let direction;
      const calculatedNextSlide = this.currentSlide + val;
      if (val > 0) {
        direction = "next";
      } else {
        direction = "previous";
      }
      if (direction === "next" && calculatedNextSlide < this.slides.length) {
        this.currentSlide += val;
      } else if (direction === "next") {
        this.currentSlide = 0;
      } else if (direction === "previous" && calculatedNextSlide < 0) {
        this.currentSlide = this.slides.length - 1;
      } else {
        this.currentSlide += val;
      }
    }
  },
};
</script>
