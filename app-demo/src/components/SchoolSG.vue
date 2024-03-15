<template>
  <div class="school-teams-section" ref="schoolTeamsSection">
    <div class="school-teams-col" ref="schoolTeamsCol">
      <div class="first-col">
        <h2>School Teams</h2>
        <h3>Customize SyncGrades to best meet your unique needs.</h3>
        <p>
          Tailor your Sync Grades settings based on your grading system, school
          needs, and user preferences.
        </p>
      </div>
      <div class="second-col">
        <img src="../assets/school-team-image.png" alt="feature" />
      </div>
    </div>
  </div>
</template>

<script>
import gsap from "gsap";

export default {
  name: "SchoolSG",
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
    observer.observe(this.$refs.schoolTeamsSection);
  },
  methods: {
    animateHeading() {
      // GSAP Animation
      gsap.from(this.$refs.schoolTeamsCol, {
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
.school-teams-section {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 80px 10px;

  .school-teams-col {
    z-index: 50;
    width: 1200px;
    display: flex;
    justify-content: space-between;

    .first-col {
      display: flex;
      justify-content: center;
      flex-direction: column;
      padding: 30px;

      h2 {
        font-size: 3em;
        font-weight: 700;
        margin-bottom: 5px;
      }

      h3 {
        font-size: 2em;
        font-weight: 500;
        margin-bottom: 5px;
      }

      p {
        font-size: 1.2em;
        font-weight: 500;
        color: #666;
        margin-bottom: 20px;
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
  .school-teams-section {
    .school-teams-col {
      .first-col {
        width: 50%;
      }
    }
  }
}
@media screen and (max-width: 768px) {
  .school-teams-section {
    .school-teams-col {
      margin-bottom: -100px;
      flex-direction: column;
      .first-col {
        width: 100%;
      }
      .second-col {
        width: 100%;
      }
    }
  }
}
@media screen and (max-width: 425px) {
  .school-teams-section {
    .school-teams-col {
      flex-direction: column;
      .first-col {
        padding: 20px;
        h2 {
          font-size: 2.5em;
        }
        h3 {
          font-size: 1.8em;
        }
        p {
          font-size: 1.2em;
        }
      }
    }
  }
}
</style>
