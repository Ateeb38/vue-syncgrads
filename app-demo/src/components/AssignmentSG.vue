<template>
  <div
    class="manage-assignments-section container-fluid align-items-center"
    ref="manageAssignmentsSection"
  >
    <!-- <img src="../assets/hero-bg-three.png" alt="" /> -->
    <div class="manage-assignments-col row" ref="manageAssignmentsCol">
      <div class="model-box model">
        <h2>Manage Assignments And Grades With one platform</h2>
        <p>
          Synchronize assignment and grade data across Google Classroom™ and
          your student information system. Enhance teacher efficiency on
          assignments, grading, report cards, and student performance in one
          place.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import gsap from "gsap";
export default {
  name: "AssignmentSG",
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
    observer.observe(this.$refs.manageAssignmentsSection);
  },
  methods: {
    animateHeading() {
      // GSAP Animation
      gsap.from(this.$refs.manageAssignmentsCol, {
        duration: 1.5,
        y: 50,
        opacity: 0,
        delay: 1,
        ease: "power1.inOut",
      });
    },
  },
};
</script>

<style scoped>
.manage-assignments-section {
  background: url("../assets/hero-bg-three.png");
  height: 160vh;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: top center;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 50px 10px;
  position: relative;
  margin: -35vh 0 -35vh 0;
  z-index: 0;

  img {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
    z-index: -1;
  }

  .manage-assignments-col {
    /* transform: rotate(90deg); */
    width: 1200px;
    display: flex;
    justify-content: center;
    align-items: center;

    .model-box {
      width: 70%;
      display: flex;
      justify-content: center;
      flex-direction: column;
      text-align: center;
      border: #ebefff;
      background: rgba(152, 169, 255, 0.08);
      padding: 100px 50px;
      border-radius: 2em;

      h2 {
        font-size: 3em;
        font-weight: 700;
        margin-bottom: 5px;
        color: #ebefff;
      }

      p {
        font-size: 1.2em;
        font-weight: 500;
        color: #e2e2e2;
        margin-bottom: 20px;
      }
    }
  }
}

@media screen and (max-width: 1024px) {
  .manage-assignments-section {
    .manage-assignments-col {
      /* transform: rotate(90deg); */
      width: 100%;
      .model-box {
        width: 70%;
        h2 {
          font-size: 2.5em;
        }
      }
    }
  }
}
@media screen and (max-width: 768px) {
  .manage-assignments-section {
    padding: 5px;
    img {
      transform: translate(-50%, -50%) scale(1.2);
      width: 150%;
    }
    .manage-assignments-col {
      .model-box {
        padding: 40px;
        width: 90%;
        h2 {
          font-size: 2.2em;
        }
      }
    }
  }
}
@media screen and (max-width: 425px) {
  .manage-assignments-section {
    padding: 5px;
    img {
      transform: translate(-50%, -50%) scale(1.8);
    }
    .manage-assignments-col {
      .model-box {
        padding: 20px;
        width: 100%;
        h2 {
          font-size: 1.8em;
        }
      }
    }
  }
}
</style>
