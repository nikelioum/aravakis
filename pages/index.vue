<template>
 <div>
  <Navbar/>
  <Mainslider/>
  <Homeabout/>
  <HomeServices/>
  <Footer/>
 </div>
</template>

<script>
export default {
  transition: 'home',

  head: {
    title: 'Home page',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Home page description'
      }
    ],
  }
}
</script>

<style scoped>
.home-enter-active, .home-leave-active { transition: opacity .5s; }
.home-enter, .home-leave-active { opacity: 0; }
</style>
