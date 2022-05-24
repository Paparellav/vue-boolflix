<template>
  <div class="main__card">
    <ul class="main__card-menu">
      <li>{{ cardObj.title ? cardObj.title : cardObj.name }}</li>
      <li>
        {{
          cardObj.original_title
            ? cardObj.original_title
            : cardObj.original_name
        }}
      </li>
      <li>
        <span class="fi" :class="`fi-${flagsUrl}`"></span>
        {{ cardObj.original_language }}
      </li>
      <li>{{ cardObj.vote_average }}</li>
      <li>
        <img
          :src="`https://image.tmdb.org/t/p/w342/${cardObj.poster_path}`"
          :alt="cardObj.title ? cardObj.title : cardObj.name"
        />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "AppCard",
  props: {
    cardObj: Object,
  },
  data: function () {
    return {};
  },
  computed: {
    flagsUrl: function () {
      switch (this.cardObj.original_language) {
        case "ru":
          return "ru";
        case "de":
          return "de";
        case "fr":
          return "fr";
        case "it":
          return "it";
        case "en":
          return "gb";
        case "es":
          return "es";
        case "pl":
          return "pl";
        case "uk":
          return "ua";
        case "ro":
          return "ro";
        case "nl":
          return "nl";
        case "tr":
          return "tr";
        case "el":
          return "gr";
        case "hu":
          return "hu";
        case "sv":
          return "se";
        case "cs":
          return "cz";
        case "pt":
          return "pt";
        case "sr":
          return "rs";
        case "bg":
          return "bg";
        case "hr":
          return "hr";
        case "da":
          return "dk";
        case "fi":
          return "fi";
        case "sq":
          return "al";
        case "no":
          return "no";
        case "sk":
          return "sk";
        case "zh":
          return "cn";
        case "hi":
          return "in";
        case "bn":
          return "bd";
        case "ja":
          return "jp";
        case "ko":
          return "kr";
        case "pa":
          return "in";
        case "ur":
          return "pk";
        case "ta":
          return "in";
        case "vi":
          return "vn";
        case "mr":
          return "in";
        case "te":
          return "in";
        case "jv":
          return "id";
        case "ar":
          return "ara";
        case "fa":
          return "ir";
        default:
          return "unknown";
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "~flag-icons/css/flag-icons.css";

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

      :first-child {
        width: 20px;
        height: 20px;
      }
    }
  }
}
</style>
