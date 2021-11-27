<template>
<div class="container-fluid">
<div class="row">
  <p v-if="$fetchState.pending"><Loader/></p>
  <p v-else-if="$fetchState.error">An error occurred :(</p>
  
  <div class="swiper">
    <div class="swiper-wrapper">

      <div class="swiper-slide swiper-slide_1">
        <div class="slider-content">
            <h1 class="text-center">Ανακαίνιση σπιτιού</h1>
            <h3 class="text-center">σύμφωνα με τις ανάγκες σας</h3>
        </div>
      </div>

       <div class="swiper-slide swiper-slide_2">
        <div class="slider-content">
            <h1 class="text-center">Ανακαινίστε το μπάνιο σας</h1>
            <h3 class="text-center">με μοντέρνες γραμμές</h3>
        </div>
      </div>
      
    </div>
    <!-- If pagination is needed -->
    <div class="swiper-pagination"></div>

  </div>
  </div>
  </div>
</template>

<script>
// import Swiper JS
// add or remove unused modules
import { Swiper, Navigation, Pagination, Autoplay } from 'swiper'
import 'swiper/swiper-bundle.min.css'
export default {

    data() {
      return {
        mountains: []
      }
    },
    async fetch() {
      this.mountains = await fetch(
        'https://wordpress-534216-2279478.cloudwaysapps.com/wp-json/wp/v2/banners?author=1?_fields=acf&acf_format=standard'
      ).then(res => res.json())
    },
  
  mounted() {
    // configure Swiper to use modules. The modules were tested with SwiperJS v6.8.4 with NuxtJS v2.15.7
    // previously it was before export default. Moved here for performance issues. Move back in case of problems.
    // add or remove unused modules
    Swiper.use([Navigation, Pagination, Autoplay])
    
    // init Swiper:
    /* eslint-disable no-unused-vars */
    const swiper = new Swiper('.swiper', {
      // Optional parameters
      // @see https://swiperjs.com/swiper-api#parameters
      direction: 'vertical',
      loop: true,
      // remove unused modules if needed
      modules: [Navigation, Pagination, Autoplay],
      // Pagination if needed
      pagination: {
        el: '.swiper-pagination',
        type: 'bullets',
        clickable: true
      },
      // Autoplay if needed
      autoplay: {
        delay: 9000
      },
      // Navigation arrows if needed
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev'
      }
      // Configure other options. Not tested
    })
  }
}
</script>

<style scoped>

h1.text-center {
    font-family: 'Ubuntu Mono';
}

h3.text-center {
    font-family: 'Ubuntu Mono';
}


.swiper {
  height: 900px;
  overflow: hidden;
  position: relative;
}
.swiper-slide_1 {
  align-items: center;
  display: flex;
  justify-content: center;
  background-image: url("https://wordpress-534216-2279478.cloudwaysapps.com/wp-content/uploads/2021/11/pexels-mark-mccammon-2724749.jpg");
}

.swiper-slide_2 {
  align-items: center;
  display: flex;
  justify-content: center;
  background-image: url("https://wordpress-534216-2279478.cloudwaysapps.com/wp-content/uploads/2021/11/pexels-max-vakhtbovych-6316055.jpg");
}

.slider-content {
    background-color: #f0f8ffa6;
    padding: 15px;
  
}

.swiper-pagination.swiper-pagination-clickable.swiper-pagination-bullets.swiper-pagination-vertical {
    background-color: rgb(0, 0, 0);
    padding: 10px;
}

..swiper-pagination-bullet {
    background-color: aliceblue !important;
    padding: 10px;
}
</style>