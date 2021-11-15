<template>
  <div id="DiscList">
    <div class="col-md-2" v-for="disk in disks" :key="disk.poster">
      <div class="disk">
        <img :src="disk.poster" alt="" />
        <h2>{{ disk.title }}</h2>
        <span>{{ disk.author }}</span>
        <span>{{ disk.year }}</span>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      disks: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((r) => {
        this.disks = r.data.response;
        console.log(this.disks, "POLLO");
      });
  },
};
</script>

<style>
#DiscList {
  display: flex;
  flex-direction: column;
}
</style>