<template>
  <div class="card p-2">
    <div class="container-img">
      <img :src="poster" class="card-img-top" alt="" />

      <div class="overlay">
          <h5>{{genre}}</h5>
      </div>
    </div>
    <div class="card-body text-center">
      <h4 class="card-title">{{title}}</h4>
      <h6 class="card-text">{{author}}</h6>
      <h6 class="card-text">{{year}}</h6>
    </div>
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

    .container-img{
        height: 220px;
        position: relative;

        &:hover{
          .overlay{
            opacity: 1;
          }
        }

        img{
          height: 100%;
        }

        .overlay{
          position: absolute;
          top: 0;
          left: 0;
          right: 0;
          bottom: 0;
          background-color: rgba($color: #000000, $alpha: .6);
          opacity: 0;
          display: flex;
          justify-content: center;
          align-items: center;
          color: white;
          backdrop-filter: blur(2px);
        }
    }

    .card-title{
        margin-bottom: 20px;
        color: white;
        text-transform: uppercase;
    }
}
</style>