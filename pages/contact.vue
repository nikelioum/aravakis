<template>
<div>
  <Navbar/>
  <ContactComp/>
  <Footer/>
</div>
</template>

<script>
export default {
  transition: 'home',
}
</script>

<style scoped>
.home-enter-active, .home-leave-active { transition: opacity .5s; }
.home-enter, .home-leave-active { opacity: 0; }
</style>