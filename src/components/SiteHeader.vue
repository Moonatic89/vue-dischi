<template>
  <header id="SiteHeader">
    <img src="../assets/logo.svg" alt="Spotify Logo" />
  </header>
</template>


<script>
export default {
  props: {
    logoImage: String,
  },
};
</script>

<style lang="scss">
@import "../assets/scss/colors.scss";

#SiteHeader {
  height: 70px;
  background-color: $backgroundColor;

  img {
    width: 50px;
    margin: 10px;
  }
}
</style>