<template>
  <div id="app">
    <HeaderComponent @search="filterDiscs" @searchByGenre="filterByGenre" />
    <MainSection :discs="filteredDiscs" />
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
      selected: "",
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
      let filteredValues = this.discs.filter((disc) => {
        if (this.selected === "") {
          return disc;
        } else {
          return disc.genre.toLowerCase().includes(this.selected);
        }
      });

      if (this.inputValue === "") {
        return filteredValues;
      } else {
        return filteredValues.filter((disc) => {
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
    filterByGenre(selected) {
      this.selected = selected;
    },
  },
};
</script>

<style lang="scss">
@import "@/sass/styles.scss";
</style>
