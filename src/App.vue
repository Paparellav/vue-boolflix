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
      const opt = {
        params: {
          api_key: "f8c2fc45385562d315d0006388000ea4",
          query: event,
        },
      };
      const req1 = axios.get("https://api.themoviedb.org/3/search/movie", opt);
      const req2 = axios.get("https://api.themoviedb.org/3/search/tv", opt);

      axios.all([req1, req2]).then((response) => {
        this.movieThumbs = response[0].data.results;
        this.tvThumbs = response[1].data.results;
      });
    },
  },
};
</script>

<style lang="scss">
@import "./style/common.scss";
</style>
