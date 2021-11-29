<template>
    <div>
          <div class="container services">
          <div class="row">
          <div class="col-md-12">
          <nav aria-label="breadcrumb" style="margin-top:100px;">
          <ol class="breadcrumb">
          <li class="breadcrumb-item"><nuxt-link to="/">Αρχική</nuxt-link></li>
          <li class="breadcrumb-item active" aria-current="page">Δείγματα Κατασκευών</li>
          </ol>
          </nav>
          </div>
          </div>
          </div>
        <div class="container services">
            <div class="row">
                <div class="col-md-12">
                    <h3 class="mb-4">Δείγματα Κατασκευών</h3>
                </div>
            </div>
            <div class="row">
            <p v-if="$fetchState.pending"><Loader/></p>
            <p v-else-if="$fetchState.error">An error occurred :(</p>
              <div v-for="mountain of mountains" class="col-md-4 d-flex align-items-stretch mb-4">  
                <div class="card shadow-sm">
                <img :src="mountain.acf.main_image" class="card-img-top" height="300">
                <div class="card-body">
                <h5 class="card-title">{{mountain.title.rendered}}</h5>
                <p class="card-text">{{mountain.acf.short_description}}</p>
                </div>
                </div>
              </div>
          </div>
        </div>
    </div>
</template>

<script> 
import NuxtLogo from './NuxtLogo.vue'
export default{
  components: { NuxtLogo },
    data() {
      return {
        mountains: []
      }
    },
    async fetch() {
      this.mountains = await fetch(
        'https://wordpress-534216-2279478.cloudwaysapps.com/wp-json/wp/v2/portfolio?author=1?_fields=acf&acf_format=standard'
      ).then(res => res.json())
    }

}
</script>

<style scoped>
.services{
    font-family: 'Ubuntu Mono';
    margin-top: 30px;
}

.breadcrumb-item>a.nuxt-link-active {
    color: #737373;
    font-weight: 700;
}

.card {
    border-left: none;
    border-right: none;
    border-top: none;
}
</style>