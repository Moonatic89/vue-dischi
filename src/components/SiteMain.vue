<template>
  <main id="SiteMain">
    <div class="container">
      <DiscList />
    </div>
  </main>
</template>

<script>
import DiscList from "./DiscList.vue";

export default {
  data() {
    return {
      diskFilter: this.genreFilter,
    };
  },
  props: {
    genreFilter: String,
  },
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