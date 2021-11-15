<template>
  <div id="DiscList">
    <div class="row">
      <div class="card" v-for="disk in disks" :key="disk.poster">
        <div class="disk">
          <img :src="disk.poster" alt="" />
          <div class="text">
            <h2>{{ disk.title }}</h2>
            <span>{{ disk.author }}</span>
            <span>{{ disk.year }}</span>
          </div>
        </div>
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

<style lang="scss">
@import "../assets/scss/colors.scss";

#DiscList {
  .row {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;

    .card {
      background-color: $primaryColor;
      width: 200px;
      margin: 2rem;
      .disk {
        padding: 0.5rem 1rem;

        img {
          width: 100%;
        }

        .text {
          display: flex;
          flex-direction: column;
          align-items: center;

          h2 {
            margin: 1rem 0;
          }
        }
      }
    }
  }
}
</style>