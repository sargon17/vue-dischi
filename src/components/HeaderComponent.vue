<template>
  <div>
    <b-navbar toggleable="lg" type="light" variant="primary" class="header">
      <b-navbar-brand>
        <img
          class="logo"
          src="http://1000logos.net/wp-content/uploads/2017/08/Spotify-Logo.png"
          alt="Spotyfy logo"
        />
      </b-navbar-brand>
    </b-navbar>
  </div>
</template>

<script>
import { BNavbar, BNavbarBrand } from "bootstrap-vue";

export default {
  name: "HeaderComponent",
  components: {
    BNavbar,
    BNavbarBrand,
  },
};
</script>

<style lang="scss">
@import "@/sass/styles.scss";

.header {
  background-color: $gray-800 !important;

  .logo {
    width: 100px;
  }
}
</style>
