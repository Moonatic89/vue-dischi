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

  components: {
    SiteHeader,
    SiteMain,
  },
  methods: {
    test() {
      console.log();
    },
  },
};
</script>

<style lang="scss">
@import "./assets/scss/common.scss";
</style>
