<template>
  <main id="SiteMain">
    <DiscList />
  </main>
</template>

<script>
import DiscList from "./DiscList.vue";

export default {
  components: {
    DiscList,
  },
};
</script>

<style lang="scss">
@import "../assets/scss/colors.scss";

#SiteMain {
  height: calc(100vh - 70px);
  background-color: $backgroundColor;
}
</style>