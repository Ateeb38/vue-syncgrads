<template>
  <div id="app">
    <!-- header new -->
    <HeaderSG />

    <!-- hero section -->
    <ContactHero />

    <!-- <Contact form /> -->
    <div class="contact-section" ref="contactSection">
      <div class="contact-col" ref="contactCol">
        <div class="first-col">
          <h2>Reach Out</h2>
          <p>Fill out the form to start using SyncGrades!</p>

          <div class="contact-info">
            <div class="contact-info-email">
              <a href="mailto:support@syncgrades.com" class="icon-box"
                ><img src="../assets/contact-icons (2).png" alt="email"
              /></a>
              <a class="contact-text" href="mailto:support@syncgrades.com"
                >support@syncgrades.com</a
              >
            </div>
            <div class="contact-info-address">
              <a class="icon-box"
                ><img src="../assets/contact-icons (1).png" alt="address"
              /></a>
              <a class="contact-text"
                >112 W. 34th Street, Suite 17059 New York, NY 10120</a
              >
            </div>
          </div>
        </div>
        <div class="second-col">
          <form>
            <div>
              <label>
                <img src="../assets/form-icons (2).png" alt="name" />Full Name
              </label>
              <input type="text" />
            </div>
            <div>
              <label>
                <img src="../assets/form-icons (1).png" alt="name" />Email
              </label>
              <input type="email" />
            </div>
            <div>
              <label>
                <img src="../assets/form-icons (3).png" alt="name" />Your
                Message
              </label>
              <textarea name="" id="" cols="30" rows="5"></textarea>
            </div>
            <div class="form-submit-button-box">
              <input type="submit" value="Submit" />
            </div>
          </form>
          <div class="extra-details">
            <p>
              Already a SyncGrades User? Visit <a href="/support">Support</a>
            </p>
            <div class="social-links">
              <a href=""><img src="../assets/fb-icon.png" alt="facebook" /></a>

              <a href=""
                ><img src="../assets/insta-icon.png" alt="instagram"
              /></a>

              <a href=""
                ><img src="../assets/linkedin-icon.png" alt="linkedin"
              /></a>
            </div>
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
import ContactHero from "./ContactHero.vue";
import FooterSG from "./FooterSG.vue";

import gsap from "gsap";

export default {
  name: "Contact",
  components: {
    HeaderSG,
    ContactHero,
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
    observer.observe(this.$refs.contactSection);
  },
  methods: {
    animateHeading() {
      // GSAP Animation
      gsap.from(this.$refs.contactCol, {
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

.social-links {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
  width: 100%;

  img {
    width: 40px !important;
    background: #2b304e;
    border-radius: 10px;
  }
}

.contact-section {
  display: flex;
  justify-content: center;
  /* align-items: center; */
  flex-direction: row;
  width: 100%;

  .contact-col {
    width: 1200px;
    display: flex;
    justify-content: space-between;
    padding: 70px 10px;

    .first-col {
      display: flex;
      justify-content: start;
      /* align-items: start; */
      flex-direction: column;
      width: 50%;
      padding: 30px;

      h2 {
        font-size: 3.5em;
        font-weight: 700;
        margin-bottom: 5px;
      }

      p {
        font-size: 1.8em;
        font-weight: 500;
        color: #292929;
        margin-bottom: 20px;
      }

      .contact-info {
        display: flex;
        flex-direction: column;
        gap: 20px;
        margin-top: 30px;

        .contact-info-email {
          display: flex;
          align-items: center;
          gap: 10px;
          .icon-box {
            width: 70px;
            height: 70px;
            background: #dfe4ff;
            border-radius: 100px;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-right: 10px;
            img {
              width: 50%;
            }
          }
          .contact-text {
            font-size: 1.5em;
            font-weight: 500;
            color: #292929;
          }
        }

        .contact-info-address {
          display: flex;
          align-items: center;
          gap: 10px;
          margin-top: 10px;

          .icon-box {
            width: 90px;
            height: 70px;
            background: #dfe4ff;
            border-radius: 100px;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-right: 10px;
            img {
              width: 50%;
            }
          }
          .contact-text {
            font-size: 1.5em;
            font-weight: 500;
            color: #292929;
          }
        }
      }
    }

    .second-col {
      display: flex;
      justify-content: center;
      /* align-items: center; */
      flex-direction: column;
      width: 50%;

      form {
        background-color: #dfe4ff;
        box-shadow: 0px 0px 20px 0px rgba(0, 0, 0, 0.1);
        padding: 40px;
        border-radius: 10px;
        width: 100%;
        margin-bottom: 20px;
        align-items: center;

        div label {
          width: 100%;
          display: flex;
          align-items: center;
          gap: 10px;
          font-size: 1.3em;
          font-weight: 500;
          color: #2b304e;
          margin-top: 20px;

          img {
            width: 20px;
          }
        }
        input,
        textarea {
          width: 100%;
          border-radius: 5px;
          background: white;
          padding: 10px;
          outline: none;
          border: none;
        }

        input[type="submit"] {
          width: 200px;
          padding: 10px 40px;
          background: linear-gradient(to right, #1b84ff, #56a3fe);
          box-shadow: 0px 0px 20px 0px rgba(0, 0, 0, 0.1);
          color: white;
          font-size: 1.3em;
          font-weight: 500;
          border-radius: 1em;
          margin-top: 10px;
          cursor: pointer;
          transition: 0.3s;
        }

        .form-submit-button-box {
          display: flex;
          justify-content: center;
          align-items: center;
        }
      }
      .extra-details {
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
        width: 100%;
        margin-top: 20px;

        p {
          font-size: 1.5em;
          font-weight: 500;
          color: #292929;
        }
      }
    }
  }
}

@media screen and (max-width: 1024px) {
  .contact-section {
    padding: 50px 10px;
    .contact-col {
      width: 100%;
      padding: 20px;

      .first-col {
        padding: 20px;
        h2 {
          font-size: 2.5em;
        }

        p {
          font-size: 1.2em;
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
  .contact-section {
    justify-content: center;
    align-items: center;
    padding: 10px;
    .contact-col {
      flex-direction: column;
      .first-col {
        width: 100%;
        .contact-info {
          .contact-info-address {
            display: flex;
            align-items: center;
            gap: 10px;
            .icon-box {
              width: 72px;
              height: 70px;
            }
          }
        }
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
  .contact-section {
    padding: 10px;
    .contact-col {
      padding: 5px;
      .first-col {
        padding: 20px 10px;

        .contact-info {
          .contact-info-address {
            display: flex;
            align-items: center;
            gap: 10px;
            .icon-box {
              width: 132px;
              height: 70px;
            }
          }
        }
      }
      .second-col {
        .extra-details {
          padding: 10px 20px;
          p {
            text-align: center;
          }
        }
      }
    }
  }
}
</style>
