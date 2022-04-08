<template>
  <div id="app">
    <HeaderComponent />
    <MainSection />
  </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import MainSection from "./components/MainSection.vue";

export default {
  name: "App",
  components: {
    HeaderComponent,
    MainSection,
  },
};
</script>

<style lang="scss">
@import "@/sass/styles.scss";
</style>
