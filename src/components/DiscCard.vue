<template>
  <div class="sf-card">
    <div class="card-content">
      <div class="card-image">
        <img :src="poster" />
      </div>
      <div class="disc-title">
        <h3>{{ title }}</h3>
      </div>
      <div class="disc-author">
        <h4>{{ author }}</h4>
      </div>
      <div class="disc-year">
        <h4>{{ year }}</h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DiscCard",
  props: {
    poster: String,
    title: String,
    author: String,
    year: String,
  },
};
</script>

<style lang="scss">
@import "@/sass/styles.scss";

.sf-card {
  width: calc(100% / 5 - 20px);
  height: 350px;
  background-color: $bg-clear-blue;
  text-align: center;
}
.card-content {
  width: 100%;
  height: 100%;
  padding: 20px;
  .card-image {
    width: 100%;
    aspect-ratio: 1;
    img {
      width: 100%;
      height: 100%;
    }
  }
  .disc-title {
    h3 {
      text-transform: uppercase;
      font-size: 1.2rem;
      font-weight: bold;
      color: $text-white;
      font-weight: $title-weight;
      margin: 10px 0;
    }
  }
  .disc-author *,
  .disc-year * {
    font-size: 1.2rem;
    font-weight: bold;
    color: $text-gray;
    font-weight: $subtitle-weight;
    font-size: 0.9rem;
  }
}
</style>
