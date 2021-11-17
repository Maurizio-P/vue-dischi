<template>
  <div class="bg-color">
    <div class="container">
      <SelectGenre @currentGenre="saveGenre" :generi="filterGenre" />
      <div class="row row-cols-5">
        <div class="col mb-3" v-for="(album, i) in selectionHandler" :key="i">
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
    <Loader v-if="loading" />
  </div>
</template>

<script>
import AlbumCard from "./AlbumCard.vue";
import Loader from "./Loader.vue"
import SelectGenre from "./SelectGenre.vue"
import axios from "axios";
export default {
  name: "ContainerAlbum",
  components: {
    AlbumCard,
    Loader,
    SelectGenre
  },

  data() {
    return {
      arrayAlbum: [],
      loading: true,
      filterSelectGenre: "",
      arrayfilter: []
    };
  },

  methods: {
    callAxios(url){
      this.loading=true
      axios.get(url).then((resp) => {
        this.arrayAlbum = resp.data.response;
        setTimeout(() => {
          this.loading=false;
        }, 1000);
      });
    },

    saveGenre(genre) {
      this.filterSelectGenre = genre
    }

  },

  mounted() {
    this.callAxios("https://flynn.boolean.careers/exercises/api/array/music")
  },

  computed: {
    filterGenre(){
      const genreDup = this.arrayAlbum.map((album) => {
        return album.genre
      })
      const generi= []
      for (let i = 0; i < genreDup.length; i++) {
        const genre = genreDup[i];
        if (!generi.includes(genre)) {
          generi.push(genre)
        } 
      }
      return generi
    },

    selectionHandler() {
      if (!this.filterSelectGenre) {
        return this.arrayAlbum
      }
      return this.arrayAlbum.filter((album) => {
        return this.filterSelectGenre === album.genre
        
      })

    }
  }
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

.bg-color {
  background-color: #192d3b;
  padding: 25px;
}
</style>