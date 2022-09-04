<template>
  <div>
    <div class="header">
      <div class="title">
        {{ title }}
      </div>
      <div class="link">
        See all
      </div>
    </div>
    <div class="q-pl-md">
      <Carousel
        :settings="settings"
      >
        <Slide
          v-for="(slide, index) in items"
          :key="slide"
        >
          <div
            class="slide non-selectable"
            :style="{ backgroundImage: 'url(' + slide.vertical_banner + ')' }"
          >
            <q-chip
              color="primary"
              text-color="white"
              class="q-ma-none score"
            >
              {{ slide.score }}
            </q-chip>
            <div
              v-if="showPosition"
              class="position"
            >
              {{ index + 1 }}
            </div>
          </div>
        </Slide>

        <template #addons>
          <Navigation />
        </template>
      </Carousel>
    </div>
  </div>
</template>

<script>
import 'vue3-carousel/dist/carousel.css';
import {
  Carousel, Slide, Navigation,
} from 'vue3-carousel';

export default {
  name: 'FeedSection',
  components: {
    Carousel,
    Slide,
    Navigation,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
    items: {
      type: Array,
      required: true,
    },
    showPosition: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      settings: {
        itemsToShow: 2.5,
        snapAlign: 'start',
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
}

.header .title {
  color: white;
  font-size: 18px;
}

.header .link {
  color: $primary;
  font-size: 16px;
}

.slide {
  width: 90%;
  height: calc(100vw * 0.6);
  background-size: cover;
  background-position: center;
  position: relative;
}

.score {
  position: absolute;
  top: 0;
  left: 0;
  margin: 5px;
}

.position {
  position: absolute;
  color: white;
  bottom: 0;
  left: 0;
  font-size: 56px;
  line-height: 100%;
  padding-left: 5px;
  padding-bottom: 10px;
  text-shadow: 2px 2px #000000;
  font-weight: bold;
}
</style>

<style>
.carousel__prev, .carousel__prev--in-active,
.carousel__next, .carousel__next--in-active {
  display: none;
}
</style>
