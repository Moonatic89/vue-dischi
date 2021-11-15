<template>
  <div id="app">
    <SiteHeader />
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
};
</script>

<style lang="scss">
@import "./assets/scss/common.scss";
</style>
