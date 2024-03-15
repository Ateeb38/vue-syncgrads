<template>
  <div id="app">
    <!-- hero section -->
    <div
      class="hero-section"
      ref="heroSection"
    >
      <div class="inner-hero">
        <div class="hero-text" ref="heroText">
          <h1>Support</h1>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import gsap from "gsap";

export default {
  name: "SupportHero",

  mounted() {
    // Intersection Observer to detect when element enters viewport
    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          // Trigger animation when element enters viewport
          this.animateHeading();
          observer.unobserve(entry.target);
        }
      });
    });

    // Observe the hero section
    observer.observe(this.$refs.heroSection);
  },
  methods: {
    animateHeading() {
      // GSAP Animation
      gsap.from(this.$refs.heroText, {
        duration: 1,
        y: 150,
        opacity: 0,
        delay: 0.5,
        ease: "power1.inOut",
      });
    },
  },
};
</script>

<style scoped>
.hero-section {
  background-image: url("../assets/support-bg.png");
  background-size: cover;
  background-position: bottom;
  background-repeat: no-repeat;
  height: 60vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.hero-section .inner-hero {
  width: 1200px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  padding-top: 50px;
}

.hero-section .inner-hero {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  .hero-text {
    /* text-align: center; */
    h1 {
      font-size: 4em;
      font-weight: 700;
      color: #fff;
      margin-bottom: 20px;
    }
  }
}
@media screen and (max-width: 1024px) {
  .hero-section {
    .inner-hero {
      width: 50%;
      .hero-text {
        h1 {
          font-size: 3em;
        }
      }
    }
  }
}
@media screen and (max-width: 768px) {
  .hero-section {
    .inner-hero {
      flex-direction: column;

      width: 100%;
      .hero-text {
        h1 {
          font-size: 3em;
        }
      }
    }
  }
}
@media screen and (max-width: 425px) {
  .hero-section {
    .inner-hero {
      .hero-text {
        h1 {
          font-size: 2.5em;
        }
      }
    }
  }
}
</style>
