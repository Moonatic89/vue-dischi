<template>
  <div id="DiscList">
    <div class="row" v-if="!loading">
      <div class="card" v-for="disk in disks" :key="disk.poster">
        <div class="cover">
          <div class="disk">
            <img :src="disk.poster" alt="" />
            <div class="text">
              <h3>{{ disk.title.toUpperCase() }}</h3>
              <h2>{{ diskFilter }}</h2>
              <span>{{ disk.author }}</span>
              <span>{{ disk.year }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="loading" v-else>Loading...</div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  props: {
    diskFilter: String,
  },
  data() {
    return {
      disks: [],
      loading: true,
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((r) => {
        this.disks = r.data.response;
        this.loading = false;
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
    width: 90%;
    margin: auto;
    justify-content: center;

    .card {
      width: calc(100% / 6);
      margin-bottom: 1rem;

      .cover {
        height: 100%;
        margin: 1rem;
        background-color: $primaryColor;

        .disk {
          padding: 0.5rem;

          img {
            width: 100%;
          }

          .text {
            color: grey;
            display: flex;
            flex-direction: column;
            align-items: center;

            h3 {
              color: white;
              margin: 1rem 0;
              text-align: center;
            }
          }
        }
      }
    }
  }
}
</style>