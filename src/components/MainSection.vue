<template>
  <div>
    <div class="main-section">
      <DiscCard
        v-for="{ poster, title, author, year } in discs"
        :key="title + year"
        :poster="poster"
        :title="title"
        :author="author"
        :year="year"
      />
    </div>
  </div>
</template>

<script>
import DiscCard from "@/components/DiscCard.vue";

export default {
  name: "MainSection",
  components: {
    DiscCard,
  },
  props: {
    discs: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
@import "@/sass/styles.scss";

.main-section {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
  justify-content: space-around;
  margin: 0 auto;
  margin-top: 50px;
  max-width: 1200px;
}
</style>
