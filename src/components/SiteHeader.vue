<template>
  <header id="SiteHeader">
    <img src="../assets/logo.svg" alt="Spotify Logo" />
  </header>
</template>


<script>
export default {};
</script>

<style lang="scss">
@import "../assets/scss/colors.scss";

#SiteHeader {
  height: 70px;
  background-color: $primaryColor;

  img {
    width: 50px;
    margin: 10px;
  }
}
</style>