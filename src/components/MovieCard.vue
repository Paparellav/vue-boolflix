<template>
  <div class="main__card">
    <ul class="main__card-menu">
      <li>{{ movie.title }}</li>
      <li>{{ movie.original_title }}</li>
      <li>{{ movie.original_language }}</li>
      <li>{{ movie.vote_average }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "MovieCard",
  props: {
    movie: Object,
  },
  data: function () {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.main__card {
  width: calc(100% / 6 - 2rem);
  height: 300px;
  padding: 1rem;
  margin: 1rem 1rem;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  border: 2px solid #b82b28;

  &-menu {
    padding: 0 1rem;
    font-size: 1.25rem;

    li {
      margin: 0.8rem 0;
    }
  }
}
</style>
