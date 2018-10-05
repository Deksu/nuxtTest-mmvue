<template>
    <Swiper/>
</template>

<script>
import Swiper from '~/components/Swiper.vue'

  export default {
      components: {
          Swiper
      }
}

</script>


<style scoped>

  .my-swiper {
    height: 300px;
    width: 100%;
  }

.swiper-slide {
    text-align: center;
    font-size: 38px;
    font-weight: 700;
    background-color: #eee;
    display: flex;
    justify-content: center;
    align-items: center;
}

</style>