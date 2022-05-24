<template>
  <div id="app">
    <AppHeader @parolaCercata="filterMovie($event)" />
    <main>
      <AppMain :movieArray="movieThumbs" :tvArray="tvThumbs" />
    </main>
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    AppHeader,
    AppMain,
  },
  data: function () {
    return {
      movieThumbs: [],
      tvThumbs: [],
      searchedWord: "",
    };
  },
  methods: {
    filterMovie(event) {
      this.searchedWord = event;
      axios
        .get("https://api.themoviedb.org/3/search/movie", {
          params: {
            api_key: "f8c2fc45385562d315d0006388000ea4",
            query: event,
          },
        })
        .then((response) => {
          this.movieThumbs = response.data.results;
        });
      axios
        .get("https://api.themoviedb.org/3/search/tv", {
          params: {
            api_key: "f8c2fc45385562d315d0006388000ea4",
            query: event,
          },
        })
        .then((response) => {
          this.tvThumbs = response.data.results;
          console.log(this.tvThumbs);
        });
    },
  },
};
</script>

<style lang="scss">
@import "./style/common.scss";
</style>
