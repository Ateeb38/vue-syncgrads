<template>
  <div class="hero-section" ref="heroSection">
    <div class="inner-hero">
      <div class="left-col">
        <div class="hero-text" ref="heroText">
          <h1>Use SyncGrades Right Now</h1>
          <p>Custom Data Solutions for Schools & Districts</p>
          <div class="hero-btn">
            <a><button>Log In</button></a>
          </div>
        </div>
      </div>
      <div class="right-col">
        <img class="people" src="../assets/hero-people.png" alt="hero" />
        <img
          class="floating-img"
          ref="floatingImg1"
          src="../assets/hero-icon-two.png"
          alt=""
        />
        <img
          class="floating-img"
          ref="floatingImg2"
          src="../assets/hero-icon-one.png"
          alt=""
        />
      </div>
    </div>
    <div id="skew-container"></div>
  </div>
</template>

<script>
import gsap from "gsap";

export default {
  name: "HeroSG",
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
  background-image: url("../assets/hero-bg.png");
  background-size: cover;
  /* background-position: 0 -88vh; */
  background-position: bottom;
  background-repeat: no-repeat;
  height: 110vh;
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
}

.hero-section .inner-hero .right-col {
  /* outline: 1px solid red; */
  width: 70%;
  position: relative;

  .people {
    margin-top: -80px;
    margin-left: -120px;
    width: 150%;
    user-select: none;
    pointer-events: none;
  }
  .floating-img {
    display: inline;
    user-select: none;
    pointer-events: none;
    width: 100%;
    position: absolute;
    bottom: -3em;
    left: -1.5em;
    width: 24em;
    height: auto;
  }

  .floating-img:nth-child(2) {
    bottom: -5em;
    left: 18em;
    width: 25em;
  }
}

.hero-section .inner-hero .left-col {
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

    p {
      font-size: 1.5em;
      font-weight: 500;
      color: #fff;
      margin-bottom: 20px;
    }

    .hero-btn {
      button {
        padding: 10px 30px;
        background: #1a83fe;
        color: #fff;
        border: none;
        border-radius: 1em;
        font-size: 1.2em;
        font-weight: 500;
        cursor: pointer;
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        margin-top: 20px;
        transition: all 0.2s ease-in-out;
        width: 200px;

        &:hover {
          background: #024da3;
        }
      }
    }
  }
}

.floating-img {
  animation: imgFloat 3s infinite;
  z-index: 5;
}
.floating-img:nth-child(2) {
  animation: imgFloat2 3s infinite;
}

@keyframes imgFloat {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
  100% {
    transform: translateY(0);
  }
}

@keyframes imgFloat2 {
  0% {
    transform: translateX(0);
  }
  50% {
    transform: translateX(-10px);
  }
  100% {
    transform: translateX(0);
  }
}

#skew-container {
  position: absolute;
  bottom: 0;
  left: 0;

  background-color: white;
  height: 130px;
  width: 100%;
  transform: skewY(-13deg);
  /* border: 1px solid red; */
}

@media screen and (max-width: 1300px) {
  .hero-section {
    #skew-container {
      height: 110px;
    }
  }

  .hero-section .inner-hero .right-col {
    .people {
      margin-top: -60px;
    }
  }
}

@media screen and (max-width: 1024px) {
  .hero-section {
    #skew-container {
      height: 240px;
    }
    height: 90vh;
    .inner-hero {
      .left-col {
        width: 50%;
        .hero-text {
          h1 {
            font-size: 3em;
          }
          p {
            font-size: 1.3em;
          }
          .hero-btn {
            button {
              padding: 14px 28px;
              font-size: 1.1em;
            }
          }
        }
      }
      .right-col {
        width: 50%;
        .people {
          width: 120%;
          margin-top: 70px;
          margin-left: -1.5em;
        }

        .floating-img {
          bottom: -4em;
          left: -1.5em;
          width: 20em;
        }

        .floating-img:nth-child(2) {
          bottom: -7em;
          left: 18em;
          width: 18em;
        }
      }
    }
  }
}
@media screen and (max-width: 768px) {
  .hero-section {
    #skew-container {
      height: 170px;
    }
    height: 100vh;
    padding-top: 100px;
    .inner-hero {
      flex-direction: column;

      .left-col {
        width: 100%;
        .hero-text {
          h1 {
            font-size: 2.5em;
          }
          p {
            font-size: 1.2em;
          }
          .hero-btn {
            button {
              padding: 12px 24px;
              font-size: 1em;
            }
          }
        }
      }

      .right-col {
        width: 100%;
        .people {
          width: 70%;
          margin-top: 0;
          margin-left: 0;
        }

        .floating-img {
          bottom: -4em;
          left: -1.5em;
          width: 18em;
        }

        .floating-img:nth-child(2) {
          bottom: -7em;
          left: 18em;
          width: 16em;
        }
      }
    }
  }
}
@media screen and (max-width: 425px) {
  .hero-section {
    /* background-position: bottom center; */

    #skew-container {
      height: 160px;
    }

    .inner-hero {
      .right-col {
        width: 100%;
        .people {
          width: 100%;
          margin-top: -10px;
          margin-left: 0;
        }

        .floating-img {
          bottom: -4em;
          left: -1.5em;
          width: 14em;
        }

        .floating-img:nth-child(2) {
          bottom: -3em;
          left: 12em;
          width: 12em;
        }
      }
    }
  }
}
</style>
