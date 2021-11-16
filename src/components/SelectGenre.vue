<template>
  <div class="select-option mb-3">
      <select name="Genre" id="Genre" @change="getGenre()" v-model="genre">
          <option v-for="(genre, i) in generi" :key='i' :value="genre">{{genre}}</option>
      </select>
  </div>
</template>

<script>
export default {
    name: "SelectGenre",
    data() {
        return {
            genre: ""
        }
    },
    props: {
        generi: Array
    },
    methods: {
        getGenre(){
            this.$emit("currentGenre", this.genre)
        }
    }
}
</script>

<style lang="scss">
</style>