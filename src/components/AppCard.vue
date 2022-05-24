<template>
  <div class="main__card">
    <img
      :src="`https://image.tmdb.org/t/p/w342/${
        cardObj.poster_path ? cardObj.poster_path : cardObj.backdrop_path
      }`"
      :alt="cardObj.title ? cardObj.title : cardObj.name"
    />
    <ul class="main__card-menu">
      <li>
        <p>Titolo: {{ cardObj.title ? cardObj.title : cardObj.name }}</p>
      </li>
      <li>
        <p>
          Titolo originale:
          {{
            cardObj.original_title
              ? cardObj.original_title
              : cardObj.original_name
          }}
        </p>
      </li>
      <li>
        <div>Lingua: <span class="fi" :class="`fi-${flagsUrl}`"></span></div>
      </li>
      <li>
        <div class="stars_section">
          Voto:
          <span
            class="stars_section_span gold"
            v-for="(item, index) in voteAverage"
            :key="index"
            ><i class="fas fa-star"></i
          ></span>
          <span
            class="stars_section_span"
            v-for="(item, index) in voteStars"
            :key="index"
            ><i class="fas fa-star"></i
          ></span>
        </div>
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
    return {
      voteAverage: Math.ceil(this.cardObj.vote_average / 2),
      voteStars: 5 - Math.ceil(this.cardObj.vote_average / 2),
    };
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
@import "~@fortawesome/fontawesome-free/css/all.min.css";

.main__card {
  width: calc(100% / 6 - 2rem);
  padding: 1rem;
  margin: 1rem 1rem;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  border: 2px solid #b82b28;

  &-menu {
    font-size: 0.8rem;

    li {
      margin: 0.8rem 0;
      display: flex;

      .stars_section {
        vertical-align: middle;
        &_span {
          margin-left: 0.1rem;
          i {
            margin: 0 0.03rem;
          }
        }
      }

      .gold {
        color: #febc00;
      }
    }
  }
}
</style>
