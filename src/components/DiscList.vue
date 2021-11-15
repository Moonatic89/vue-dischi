<template>
  <div id="DiscList">
    <img :src="discImg" alt="" />
    <h2>{{ discName }}</h2>
    <span>{{ discAuthor }}</span>
    <span>{{ discYear }}</span>
  </div>
</template>

<script>
export default {
  props: {
    discImg: String,
    discName: String,
    discAuthor: String,
    discYear: String,
  },
};
</script>

<style>
#DiscList {
  display: flex;
  flex-direction: column;
}
</style>