<template>
  <div id="app">
    <SiteHeader @genreFilter="test" />
    <SiteMain />
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
    test(genreString) {
      console.log(genreString);
    },
  },
};
</script>

<style lang="scss">
@import "./assets/scss/common.scss";
</style>
