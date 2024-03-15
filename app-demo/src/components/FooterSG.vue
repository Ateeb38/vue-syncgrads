<template>
  <div class="footer-section container-fluid">
    <div class="footer-col row">
      <img src="../assets/vertical-logo-syncgrades.png" alt="feature" />
      <div class="quick-links">
        <ul>
          <a href="/contact"><li>Contact Us</li></a>
          <a href="/support"><li>Support</li></a>
        </ul>
      </div>

      <div class="social-links">
        <a href=""
          ><img src="../assets/fb-icon.png" width="20px" alt="facebook"
        /></a>

        <a href=""
          ><img src="../assets/insta-icon.png" width="20px" alt="instagram"
        /></a>

        <a href=""
          ><img src="../assets/linkedin-icon.png" width="20px" alt="linkedin"
        /></a>
      </div>

      <div class="copy-right">
        <p>© 2024 SyncGrades. All rights reserved.</p>
        <div>
          <a>Privacy Policy</a>
          <a>Terms & Conditions</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FooterSG",
};
</script>

<style scoped>
.footer-section {
  background: linear-gradient(180deg, #13263c, #0a1a2e);
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 50px 10px 20px 10px;

  .footer-col {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 1200px;

    img {
      width: 300px;
      margin-bottom: 30px;
    }

    .quick-links {
      ul {
        display: flex;
        justify-content: center;
        align-items: center;
        list-style: none;
        li {
          text-transform: uppercase;
          letter-spacing: 1px;
          font-weight: 500;
          margin: 0 20px;
          cursor: pointer;
          color: #ebefff;
        }
      }
    }

    .social-links {
      display: flex;
      justify-content: center;
      align-items: center;
      margin-bottom: 20px;

      img {
        width: 30px;
        margin: 0 10px;
      }
    }

    .copy-right {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 100%;
      margin-top: 20px;
      padding-top: 20px;
      border-top: 1px dashed #68696e;

      p {
        font-size: 1em;
        font-weight: 500;
        color: #ebefff;
        margin-bottom: 20px;
        cursor: pointer;
        margin: 0 20px;
      }

      div {
        display: flex;

        a {
          letter-spacing: 1px;
          font-size: 1em;
          font-weight: 500;
          margin: 0 20px;
          cursor: pointer;
          color: #ebefff;
        }
      }
    }
  }
}

/* @media screen and (max-width: 1024px) {
} */
@media screen and (max-width: 768px) {
  .copy-right {
    flex-direction: column;
    align-items: center;
    gap: 10px;
    p {
      margin-bottom: 20px;
    }
  }
}
@media screen and (max-width: 425px) {
  .footer-section {
    .footer-col {
      img {
        width: 60%;
      }
    }
  }
}
</style>
