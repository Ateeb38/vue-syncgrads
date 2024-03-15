<template>
  <div class="features-section" ref="featuresSection">
    <div class="features-col" ref="featuresCol">
      <div class="feature-box">
        <div class="col-one">
          <h3>Course Syncing</h3>
          <p>
            Eliminate double data entry for teachers through automated data
            synchronization between Google Classroom™ and your SIS.
          </p>
        </div>
        <div class="col-two">
          <img src="../assets/feature-one-image.png" alt="feature" />
        </div>
      </div>
      <div class="feature-box">
        <div class="col-one">
          <h3>Analytics</h3>
          <p>
            Eliminate double data entry for teachers through automated data
            synchronization between Google Classroom™ and your SIS.
          </p>
        </div>
        <div class="col-two">
          <img src="../assets/feature-two-image.png" alt="feature" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import gsap from "gsap";
export default {
  name: "FeaturesSG",
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
        y: 200,
        opacity: 0,
        delay: .5,
        ease: "power1.inOut",
      });
    },
  },
};
</script>

<style scoped>
.features-section {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
  /* background: #f5f5f5; */

  .features-col {
    width: 1200px;
    display: flex;
    justify-content: space-between;
    align-items: center;

    .feature-box {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 40px;
      background: #ebefff;
      border-radius: 1em;
      box-shadow: 0 10px 20px #131a331e;
      margin: 20px;
      height: 400px;

      .col-one {
        width: 60%;
        h3 {
          font-size: 2.5em;
          font-weight: 700;
          margin-bottom: 20px;
        }

        p {
          font-size: 1.2em;
          font-weight: 500;
          color: #666;
          margin-bottom: 20px;
        }
      }

      .col-two {
        width: 40%;
        img {
          width: 100%;
        }
      }
    }
  }
}

@media screen and (max-width: 1024px) {
  .features-section {
    .features-col {
      width: 100%;
      .feature-box {
        .col-one {
          h3 {
            font-size: 2em;
          }
        }
      }
    }
  }
}
@media screen and (max-width: 768px) {
  .features-section {
    .features-col {
      .feature-box {
        flex-direction: column-reverse;
        padding: 20px;
        height: auto;
        .col-one {
          width: 100%;
          h3 {
            font-size: 2em;
          }
        }

        .col-two {
          width: 100%;
          img {
            width: 30%;
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
        }

        .col-two {
          width: 100%;
          img {
            width: 30%;
          }
        }
      }
    }
  }
}
</style>
