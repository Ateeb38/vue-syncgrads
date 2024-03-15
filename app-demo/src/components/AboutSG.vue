<template>
  <div class="about-section" ref="aboutSection">
    <div class="about-col" ref="aboutCol">
      <div class="first-col">
        <h2>Meet SyncGrades</h2>
        <p>
          Tailor your Sync Grades settings based on your grading system, school
          needs, and user preferences.
        </p>
        <button>About Us</button>
      </div>
      <div class="second-col">
        <img src="../assets/about-image.png" alt="feature" width="100%" />
      </div>
    </div>
  </div>
</template>

<script>
import gsap from "gsap";
export default {
  name: "AboutSG",
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
    observer.observe(this.$refs.aboutSection);
  },
  methods: {
    animateHeading() {
      // GSAP Animation
      gsap.from(this.$refs.aboutCol, {
        duration: 1,
        y: 150,
        opacity: 0,
        delay: 0.2,
        ease: "power1.inOut",
      });
    },
  },
};
</script>

<style scoped>
.about-section {
  display: flex;
  justify-content: center;
  align-items: center;
  .about-col {
    width: 1200px;
    display: flex;
    justify-content: space-between;
    padding: 70px 10px;

    .first-col {
      display: flex;
      justify-content: center;
      flex-direction: column;
      width: 50%;

      h2 {
        font-size: 3em;
        font-weight: 700;
        margin-bottom: 5px;
      }

      p {
        font-size: 1.2em;
        font-weight: 500;
        color: #666;
        margin-bottom: 20px;
      }

      button {
        width: 30%;
        padding: 16px 32px;
        background: #42b66a;
        color: #fff;
        border: none;
        border-radius: 2em;
        font-size: 1.2em;
        font-weight: 500;
        cursor: pointer;
        box-shadow: 0 5px 20px rgba(1, 71, 13, 0.3);
        transition: all 0.2s ease-in-out;

        &:hover {
          background-color: #17742a;
        }
      }
    }

    .second-col {
      width: 50%;
      img {
        width: 100%;
      }
    }
  }
}

@media screen and (max-width: 1024px) {
  .about-section {
    padding: 50px 10px;
    .about-col {
      width: 100%;
      padding: 20px;

      .first-col {
        padding: 20px;
        h2 {
          font-size: 2.5em;
        }

        p {
          font-size: 1em;
        }

        button {
          width: 50%;
        }
      }

      .second-col {
        width: 50%;
        img {
          width: 100%;
        }
      }
    }
  }
}
@media screen and (max-width: 768px) {
  .about-section {
    justify-content: center;
    align-items: center;
    padding: 10px;
    .about-col {
      flex-direction: column-reverse;
      .first-col {
        width: 100%;
      }
      .second-col {
        margin: 30px 0;
        width: 100%;
        img {
          width: 100%;
        }
      }
    }
  }
}
@media screen and (max-width: 425px) {
  .about-section {
    padding: 10px;
    .about-col {
      padding: 5px;
      .first-col {
        padding: 20px 10px;
      }
    }
  }
}
</style>
