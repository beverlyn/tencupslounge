<script setup lang="ts">
import NavigationBar from "./components/NavigationBar.vue";
import Hero from "./components/Hero.vue";
import About from "./components/About.vue";
import MenuDivider from "./components/MenuDivider-background.vue";
import MenuSection from "./components/MenuSection.vue";
import LineupDivider from "./components/LineupDivider.vue";
import LineUp from "./components/Lineup.vue";
import StoreInfoDivider from "./components/StoreInfoDivider.vue";
import StoreInfo from "./components/StoreInfo.vue";
import Footer from "./components/Footer.vue";

</script>

<template>
  <NavigationBar class="fixed top-0 z-[999]"/>
  <Hero id="hero"/>
  <About id="about"/>
  <MenuDivider/>
  <MenuSection id="menu"/>
  <LineupDivider/>
  <LineUp id="lineup"/>
  <StoreInfoDivider/>
  <StoreInfo id="info"/>
  <Footer/>
</template>