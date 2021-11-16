<template>
  <main id="SiteMain">
    <div class="container">
      <DiscList :diskFilter="childFilter" />
    </div>
  </main>
</template>

<script>
import DiscList from "./DiscList.vue";

export default {
  props: {
    childFilter: String,
  },
  // data() {
  //   return {
  //     diskFilter: this.childFilter,
  //   };
  // },
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