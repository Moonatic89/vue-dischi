<template>
  <header id="SiteHeader">
    <div class="logo">
      <img src="../assets/logo.svg" alt="Spotify Logo" />
    </div>
    <div class="formGroup">
      <label for="cars">Choose a car:</label>

      <select name="cars" id="cars">
        <option value="volvo">Volvo</option>
        <option value="saab">Saab</option>
        <option value="mercedes">Mercedes</option>
        <option value="audi">Audi</option>
      </select>
    </div>
  </header>
</template>


<script>
export default {};
</script>

<style lang="scss">
@import "../assets/scss/colors.scss";

#SiteHeader {
  display: flex;
  height: 70px;
  background-color: $primaryColor;

  img {
    width: 50px;
    margin: 10px;
  }
}
</style>