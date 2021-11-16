<template>
  <div id="app">
    <SiteHeader @genreFilter="genreToFilter" />
    <SiteMain :childFilter="genreFilter" />
  </div>
</template>

<script>
import SiteHeader from "./components/SiteHeader";
import SiteMain from "./components/SiteMain";
export default {
  name: "App",
  data() {
    return {
      genreFilter: "",
    };
  },
  components: {
    SiteHeader,
    SiteMain,
  },
  methods: {
    genreToFilter(text) {
      this.genreFilter = text;
    },
  },
};
</script>

<style lang="scss">
@import "./assets/scss/common.scss";
</style>
