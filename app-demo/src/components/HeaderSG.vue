<template>
  <div class="header fixed-top">
    <b-navbar class="inner-header" toggleable="lg" type="dark">
      <b-navbar-brand href="/" class="logo-box">
        <a href="/">
          <img src="../assets/logo-syncgrade.png" alt="logo" />
        </a>
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto right">
          <b-navbar-nav class="menu-items-alignment">
            <b-nav-item class="syncgrades-menu-item" href="/contact"
              ><router-link class="sg-item" to="/contact"
                >Contact Us</router-link
              ></b-nav-item
            >
            <b-nav-item class="syncgrades-menu-item" href="/support"
              ><router-link class="sg-item" to="/support"
                >Support</router-link
              ></b-nav-item
            >
            <div class="icon-box">
              <img src="../assets/login-icon.png" alt="logo" />
            </div>
          </b-navbar-nav>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: "HeaderSG",
};
</script>

<style scoped>
/* header styles */
.header {
  /* outline: 1px solid red; */
  display: flex;
  justify-content: center;
  align-items: center;
  background: transparent;
  color: aliceblue;
  z-index: 9999;
}

.inner-header {
  /* position: fixed; */
  /* outline: 1px solid red; */
  margin-bottom: -8em;
  width: 1200px;
  display: flex;
  justify-content: space-between;
  /* background: rgba(179, 179, 179, 0.568); */
  background: hsla(207, 28%, 61%, 0.6);
  border-radius: 3em;
  margin-top: 30px;
  padding: 10px 40px;
  backdrop-filter: blur(10px);
  margin-left: 20px;
  margin-right: 20px;
  box-shadow: 0 5px 20px 0 rgba(0, 0, 0, 0.3);
}

.logo-box {
  width: 250px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.logo-box img {
  width: 100%;
}

.syncgrades-menu-box {
  display: flex;
  justify-content: center;
  align-items: center;

  .icon-box {
    margin-left: 20px;
    width: 35px;
    height: 35px;
    display: flex;
    justify-content: center;
    align-items: center;
    img {
      width: 100%;
    }
  }
}

.syncgrades-menu-item {
  text-transform: uppercase;
  letter-spacing: 1px;
  font-size: 1.1em;
  font-weight: 600;
  margin: 0 10px;
  cursor: pointer;
  color: #13263c !important;
}

.sg-item {
  color: #13263c !important;
  margin-right: 10px;
}

.router-link-active {
  color: #ffffff !important;
}

.menu-items-alignment {
  text-align: end;
}

@media screen and (max-width: 768px) {
  .sg-item {
    margin-right: 0;
  }
}

@media screen and (max-width: 425px) {
  .header {
    .inner-header {
      .logo-box {
        width: 55%;
      }
    }
  }
}
</style>
