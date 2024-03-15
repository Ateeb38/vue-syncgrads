<template>
  <div id="app">
    <!-- header new -->
    <HeaderSG />

    <!-- hero section -->
    <HeroSG />

    <!-- features section -->
    <FeaturesSG />

    <!-- school teams section -->
    <SchoolSG />

    <!-- manage sections -->
    <AssignmentSG />

    <!-- time sync section -->
    <CTASG />

    <!-- about section -->
    <!-- <AboutSG /> -->

    <!-- footer-section -->
    <FooterSG />
  </div>
</template>

<script>
import HeaderSG from "./HeaderSG.vue";
import HeroSG from "./HeroSG.vue";
import FeaturesSG from "./FeaturesSG.vue";
import SchoolSG from "./SchoolSG.vue";
import AssignmentSG from "./AssignmentSG.vue";
import CTASG from "./CTASG.vue";
import AboutSG from "./AboutSG.vue";
import FooterSG from "./FooterSG.vue";

export default {
  name: "Home",
  components: {
    HeaderSG,
    HeroSG,
    FeaturesSG,
    SchoolSG,
    AssignmentSG,
    CTASG,
    AboutSG,
    FooterSG,
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
</style>
