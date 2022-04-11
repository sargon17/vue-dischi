<template>
  <div id="app">
    <HeaderComponent @search="filterDiscs" />
    <MainSection :discs="filteredDiscs" />
    <!-- <p>{{ filteredDiscs }}</p> -->
  </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import MainSection from "./components/MainSection.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    HeaderComponent,
    MainSection,
  },
  data() {
    return {
      discs: [],
      inputValue: "",
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.discs = response.data.response;
      });
  },
  computed: {
    filteredDiscs() {
      if (this.inputValue === "") {
        return this.discs;
      } else {
        return this.discs.filter((disc) => {
          return (
            disc.title.toLowerCase().includes(this.inputValue) ||
            disc.author.toLowerCase().includes(this.inputValue) ||
            disc.year.toString().includes(this.inputValue)
          );
        });
      }
    },
  },
  methods: {
    filterDiscs(inputValue) {
      this.inputValue = inputValue;
    },
  },
};
</script>

<style lang="scss">
@import "@/sass/styles.scss";
</style>
