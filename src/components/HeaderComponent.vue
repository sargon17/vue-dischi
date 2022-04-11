<template>
  <div>
    <b-navbar toggleable="lg" class="header">
      <b-navbar-brand>
        <img
          class="logo"
          src="http://1000logos.net/wp-content/uploads/2017/08/Spotify-Logo.png"
          alt="Spotyfy logo"
        />
      </b-navbar-brand>
      <b-navbar-nav class="ml-auto">
        <b-nav-form>
          <b-form-input
            size="sm"
            class="mr-sm-2"
            placeholder="Search"
            v-model="inputValue"
            @keyup="$emit('search', inputValue)"
          ></b-form-input>
          <b-button
            size="sm"
            class="my-2 my-sm-0"
            @click="$emit('search', inputValue)"
          >
            Search</b-button
          >
        </b-nav-form>
      </b-navbar-nav>
    </b-navbar>
  </div>
</template>

<script>
import {
  BNavbar,
  BNavbarBrand,
  BNavbarNav,
  BNavForm,
  BFormInput,
  BButton,
} from "bootstrap-vue";

export default {
  name: "HeaderComponent",
  data() {
    return {
      inputValue: "",
    };
  },
  components: {
    BNavbar,
    BNavbarBrand,
    BNavbarNav,
    BNavForm,
    BFormInput,
    BButton,
  },
};
</script>

<style lang="scss">
@import "@/sass/styles.scss";

.header {
  background-color: $bg-clear-blue;
  .logo {
    width: 75px;
  }
}
</style>
