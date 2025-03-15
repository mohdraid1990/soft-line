<template>
  <div class="slider">
    <div class="nav-slider">
      <div class="title-slider">
        <h1>Корпоративная жизнь</h1>
      </div>
      <div class="arrow-slider">
        <button @click.prevent="prevSlide" class="nav-btn" @mousedown.prevent>
          <img src="../assets/Rectangle 9018.svg" alt="Previous Slide" />
        </button>
        <button @click.prevent="nextSlide" class="nav-btn" @mousedown.prevent>
          <img src="../assets/Rectangle 9018 (1).svg" alt="Next Slide" />
        </button>
      </div>
    </div>

    <img
      :key="currentIndex"
      :src="images[currentIndex]"
      alt="Slide Image"
      class="slider-image fade-slide"
    />

    <div class="indicator-container">
      <span
        v-for="(image, index) in images"
        :key="index"
        :class="{ active: index === currentIndex }"
        class="indicator"
        @click.prevent="goToSlide(index)"
        @mousedown.prevent
      ></span>
    </div>
  </div>
</template>

<script>
import slide1 from "../assets/slide-1.png";
import slide2 from "../assets/slide-2.png";
import slide3 from "../assets/slide-3.png";
import slide4 from "../assets/slide-4.png";
import slide5 from "../assets/slide-5.png";

export default {
  data() {
    return {
      currentIndex: 0,
      images: [slide1, slide2, slide3, slide4, slide5],
      intervalId: null,
    };
  },
  mounted() {
    this.startAutoSlide();
  },
  beforeDestroy() {
    this.stopAutoSlide();
  },
  methods: {
    startAutoSlide() {
      this.intervalId = setInterval(() => {
        this.nextSlide();
      }, 5000);
    },
    stopAutoSlide() {
      clearInterval(this.intervalId);
      this.intervalId = null;
    },
    nextSlide() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    prevSlide() {
      this.currentIndex =
        (this.currentIndex - 1 + this.images.length) % this.images.length;
    },
    goToSlide(index) {
      this.currentIndex = index;
    },
    resetAutoSlide() {
      this.stopAutoSlide();
      this.startAutoSlide();
    },
  },
  watch: {
    currentIndex() {
      this.resetAutoSlide();
    },
  },
};
</script>

<style lang="scss" scoped>
.slider {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 91%;
  margin: 100px auto;

  // Styling for the main slider image
  .slider-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
    animation: slideFade 0.8s ease-in-out;
  }

  // Keyframe animation for slide transition
  @keyframes slideFade {
    0% {
      opacity: 0;
      transform: translateX(20px);
    }
    100% {
      opacity: 1;
      transform: translateX(0);
    }
  }

  // Container for slide indicators
  .indicator-container {
    display: flex;
    justify-content: center;
    margin-top: 20px;
    width: 100%;
    gap: 10px;

    .indicator {
      width: 214px;
      height: 6px;
      background-color: #f0f0f0;
      transition: background-color 0.3s;
      cursor: pointer;

      &.active {
        background-color: #a30c33;
      }
    }
  }

  // Navigation and title section
  .nav-slider {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;

    .title-slider {
      h1 {
        font-family: "Proxima Nova Condensed", sans-serif;
        font-size: 56px;
        font-weight: 600;
        line-height: 56px;
        text-align: left;
        color: #444444;
      }
    }

    // Navigation arrow buttons
    .arrow-slider {
      display: flex;
      align-items: center;
      gap: 20px;

      .nav-btn {
        background-color: #f0f0f0;
        border: none;
        cursor: pointer;
        width: 56px;
        height: 56px;
        border-radius: 50%;
        transition: transform 0.3s;

        &:hover {
          transform: scale(1.1);
        }
      }
    }
  }

  // Responsive adjustments
  @media (max-width: 1030px) {
    .title-slider h1 {
      font-size: 35px !important;
    }

    .indicator-container .indicator {
      width: 160px;
    }
  }

  @media (max-width: 600px) {
    .title-slider h1 {
      font-size: 23px !important;
    }

    .arrow-slider .nav-btn {
      width: 48px;
      height: 48px;
    }

    .indicator-container .indicator {
      width: 100px;
    }
  }
}
@media (max-width: 400px) {
    .slider .title-slider h1 {
        font-size: 17px !important;
    }
  }

</style>
