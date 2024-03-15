<template>
  <div id="app">
    <!-- header new -->
    <HeaderSG />

    <!-- hero section -->
    <SupportHero />

    <!-- <AboutSG /> -->
    <SupportHelp />

    <!-- cards -->
    <div class="features-section" ref="featuresSection">
      <div class="features-col" ref="featuresCol">
        <div class="feature-box">
          <div class="col-one">
            <img src="../assets/support-icons (1).png" alt="option" />
            <h3>Technical Support</h3>
            <p>
              I am having trouble and ran into an issue while using SyncGrades
            </p>
          </div>
        </div>
        <div class="feature-box">
          <div class="col-one">
            <img
              id="bulb-option"
              src="../assets/support-icons (2).png"
              alt="option"
            />
            <h3>Improvement + New Features</h3>
            <p>I Have an idea that could enhance SyncGrades</p>
          </div>
        </div>
        <div class="feature-box">
          <div class="col-one">
            <img src="../assets/support-icons (3).png" alt="option" />
            <h3>General Information and Questions</h3>
            <p>
              I have a general inquiry or questions not related to the other
              topic
            </p>
          </div>
        </div>
      </div>
    </div>

    <!-- footer-section -->
    <FooterSG />
  </div>
</template>

<script>
import HeaderSG from "./HeaderSG.vue";
import SupportHero from "./SupportHero.vue";
import SupportHelp from "./SupportHelp.vue";
import FooterSG from "./FooterSG.vue";

import gsap from "gsap";

export default {
  name: "Support",
  components: {
    HeaderSG,
    SupportHero,
    SupportHelp,
    FooterSG,
  },

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
    observer.observe(this.$refs.featuresSection);
  },
  methods: {
    animateHeading() {
      // GSAP Animation
      gsap.from(this.$refs.featuresCol, {
        duration: 1,
        y: 150,
        opacity: 0,
        delay: 1,
        ease: "power1.inOut",
      });
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow-x: hidden;
}

.features-section {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
  margin-bottom: 90px;

  /* background: #f5f5f5; */

  .features-col {
    width: 1200px;
    display: grid;
    grid-template-columns: repeat(3, 1fr);

    .feature-box {
      display: flex;
      justify-content: center;
      flex-direction: column;
      align-items: center;
      padding: 40px;
      background: #ebefff;
      border-radius: 1em;
      box-shadow: 0 10px 20px #131a331e;
      margin: 20px;
      height: 400px;

      .col-one {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        h3 {
          text-align: center;
          font-size: 2em;
          font-weight: 700;
          margin-bottom: 20px;
        }

        p {
          text-align: center;
          font-size: 1.2em;
          font-weight: 500;
          color: #666;
          margin-bottom: 20px;
        }
        img {
          width: 80px;
          margin-bottom: 20px;
        }
      }
    }
  }
}

#bulb-option {
  width: 50px;
}

@media screen and (max-width: 1024px) {
  .features-section {
    .features-col {
      width: 100%;
      .feature-box {
        .col-one {
          h3 {
            font-size: 1.8em;
          }
        }
      }
    }
  }
}
@media screen and (max-width: 768px) {
  .features-section {
    .features-col {
      grid-template-columns: repeat(1, 1fr);
      .feature-box {
        flex-direction: column;
        padding: 20px;
        height: auto;
        .col-one {
          width: 100%;
          h3 {
            font-size: 2em;
          }
          img {
            width: 80px;
          }
        }
      }
    }
  }
}
@media screen and (max-width: 425px) {
  .features-section {
    .features-col {
      flex-direction: column;
      .feature-box {
        flex-direction: column-reverse;
        padding: 20px;
        height: auto;
        .col-one {
          width: 100%;
          h3 {
            font-size: 2em;
          }
          img {
            width: 30%;
          }
        }
      }
    }
  }
}
</style>
