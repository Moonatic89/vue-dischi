<template>
  <header id="SiteHeader">
    <div class="logo">
      <img src="../assets/logo.svg" alt="Spotify Logo" />
    </div>
    <div class="formGroup">
      <label for="diskGenre">Choose a Genre to filter:</label>

      <select
        name="diskGenre"
        id="diskGenre"
        v-model="genreString"
        @change="$emit('genreFilter', genreString)"
      >
        <option selected value="All">All</option>
        <option v-for="genre in genresArr" :key="genre" :value="genre">
          {{ genre }}
        </option>
      </select>
    </div>
  </header>
</template>


<script>
import axios from "axios";
export default {
  data() {
    return {
      genresArr: [],
      authorsArr: [],
      genreString: "",
    };
  },
  methods: {
    getGenres(objs) {
      const uniqueGenres = [];
      for (let i = 0; i < objs.length; i++) {
        if (!uniqueGenres.includes(objs[i].genre)) {
          uniqueGenres.push(objs[i].genre);
        }
      }
      return uniqueGenres;
    },
    getAuthors() {},
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((r) => {
        this.genresArr = this.getGenres(r.data.response);
        console.log(this.genresArr);

        // this.genres = r.data.response.genres;
        // this.authors = r.data.response.authors;
        // console.log(this.genres, this.authors);
      });
  },
};
</script>

<style lang="scss">
@import "../assets/scss/colors.scss";

#SiteHeader {
  display: flex;
  align-items: center;
  height: 70px;
  background-color: $primaryColor;

  label {
    color: white;
    padding: 1rem;
  }

  img {
    width: 50px;
    margin: 10px;
  }
}
</style>