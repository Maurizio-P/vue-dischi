<template>
  <div class="bg-color">
    <div class="container">
      <div class="row row-cols-5">
        <div class="col mb-3" v-for="(album, i) in arrayAlbum" :key="i">
          <AlbumCard
            :title="album.title"
            :author="album.author"
            :poster="album.poster"
            :year="album.year"
            :genre="album.genre"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AlbumCard from "./AlbumCard.vue";
import axios from "axios";
export default {
  name: "ContainerAlbum",
  components: {
    AlbumCard,
  },
  data() {
    return {
      arrayAlbum: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.arrayAlbum = resp.data.response;
      });
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

.bg-color {
  background-color: #192d3b;
  padding: 25px;
}
</style>