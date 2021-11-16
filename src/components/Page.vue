<template>
<div>
  <div class="top-bar">
      <img src="https://www.ore25.it/wp-content/uploads/2020/01/file-spotify-logo-png-4.png" alt="">
  </div>
  <ContainerAlbum /> 
</div>
</template>

<script>
import ContainerAlbum from './ContainerAlbum.vue'
export default {
    name: "Page",
    components: {
        ContainerAlbum
    }
}
</script>

<style lang="scss">

    .top-bar{
        background-color: #2b3a46;
        padding: 10px;

        img{
            height: 50px;
            margin-left: 10px;
        }
    }
</style>