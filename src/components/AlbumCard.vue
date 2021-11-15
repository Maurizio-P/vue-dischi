<template>
  <div class="card p-2">
    <img :src="poster" class="card-img-top" alt="" />
    <div class="card-body text-center">
      <h4 class="card-title">{{title}}</h4>
      <h6 class="card-text">{{author}}</h6>
      <h6 class="card-text">{{year}}</h6>
    </div>
    <!-- <div class="overlay">
        <h5>{{genre}}</h5>
    </div> -->
  </div>
</template>

<script>
export default {
  name: "AlbumCard",
  props: {
    title: String,
    author: String,
    poster: String,
    year: String,
    genre: String,
  },
};
</script>

<style lang="scss">
.card{
    background-color: #2b3a46!important;
    height: 100%;
    color: #7f7d7b;

    img{
        height: 220px;
    }

    .card-title{
        margin-bottom: 20px;
        color: white;
    }
}
</style>