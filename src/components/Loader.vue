<template>
  <div class="loader">
      <img src="https://www.ore25.it/wp-content/uploads/2020/01/file-spotify-logo-png-4.png" alt="">
  </div>
</template>

<script>
export default {
    name: "Loader"
}
</script>

<style lang="scss">
    .loader{
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: #192d3b;
        display: flex;
        justify-content: center;
        align-items: center;

        img{
            height: 500px;
            animation: rotate 3s infinite ;
        }
    }

    @keyframes rotate {
        from{
            transform: rotate(0deg);
        }
        to {
            transform: rotate(360deg);
        }
        

}
</style>