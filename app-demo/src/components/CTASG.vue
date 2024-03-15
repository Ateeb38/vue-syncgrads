<template>
  <div class="time-sync-section" ref="timeSyncSection">
    <div class="time-sync-col" ref="timeSyncCol">
      <h2>Time To Sync</h2>

      <div class="time-sync-second-col">
        <p>
          Let SyncGrades enhance your student management system and empower your
          school community
        </p>
        <button>Contact Us</button>
      </div>
    </div>
  </div>
</template>

<script>
import gsap from "gsap";
export default {
  name: "CTASG",
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
    observer.observe(this.$refs.timeSyncSection);
  },
  methods: {
    animateHeading() {
      // GSAP Animation
      gsap.from(this.$refs.timeSyncCol, {
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
.time-sync-section {
  margin: 80px;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 80px 10px;
  margin-top: 40px;

  .time-sync-col {
    z-index: 50;
    width: 1200px;
    background: linear-gradient(to right, #2baa45, #23a680);
    display: flex;
    justify-content: start;
    align-items: start;
    flex-direction: column;
    border-radius: 2em;
    padding: 50px;
    box-shadow: 0 10px 20px #04380e25;

    h2 {
      font-size: 3em;
      font-weight: 700;
      margin-bottom: 5px;
      color: #ffffff;
    }

    .time-sync-second-col {
      display: flex;
      justify-content: start;
      align-items: center;

      p {
        font-size: 1.4em;
        font-weight: 500;
        color: #ffffff;
        margin-bottom: 20px;
        padding-right: 40px;
        width: 70%;
      }

      button {
        width: 30%;
        padding: 16px 32px;
        background: #42b66a;
        color: #fff;
        border: none;
        border-radius: 1em;
        font-size: 1.4em;
        font-weight: 500;
        cursor: pointer;
        box-shadow: 0 5px 20px rgba(1, 71, 13, 0.5);
        transition: all 0.2s ease-in-out;

        &:hover {
          background: #17742a;
        }
      }
    }
  }
}

@media screen and (max-width: 1024px) {
  .time-sync-section {
    margin: 30px 10px;

    padding: 15px;
    .time-sync-col {
      padding: 40px;
      width: 100%;
    }
  }
}
@media screen and (max-width: 768px) {
  .time-sync-section {
    .time-sync-col {
      .time-sync-second-col {
        align-items: start;
        justify-content: start;
        flex-direction: column;

        p {
          width: 100%;
        }
        button {
          width: fit-content;
        
        }
      }
    }
  }
}
@media screen and (max-width: 425px) {
  .time-sync-section {
    padding: 5px;

    .time-sync-col {
      padding: 35px;

      h2 {
        font-size: 2.5em;
      }

      .time-sync-second-col {
        p {
          font-size: 1.2em;
          width: 100%;
        }

        button {
          width: 100%;
        }
      }
    }
  }
}
</style>
