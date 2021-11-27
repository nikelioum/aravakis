<template>
    <div>
      <div class="container home-services text-center">
          <div class="row">
              <div class="col-md-12 mb-3">
                  <h3>Πακέτα Ανακαίνισης</h3>
              </div>
          </div>
          <div class="row">
              <div v-for="mountain of mountains" class="col-md-4 d-flex align-items-stretch mb-4">
                <div class="card shadow-sm">
                <img :src="mountain.acf.image" class="card-img-top" alt="">
                <div class="card-body">
                <h5 class="card-title">{{mountain.acf.title}}</h5>
                <p class="card-text">{{mountain.acf.description}}</p>
                <nuxt-link to="" class="btn btn-outline-dark btn-phone-dark">Περισσότερα</nuxt-link>
                </div>
                </div>
            </div>
          </div>
      </div>    
    </div>
</template>

<script>
export default {
    data() {
      return {
        mountains: []
      }
    },
    async fetch() {
      this.mountains = await fetch(
        'https://wordpress-534216-2279478.cloudwaysapps.com/wp-json/wp/v2/paketa?author=1?_fields=acf&acf_format=standard'
      ).then(res => res.json())
    }
  }
</script>

<style scoped>
.home-services{
    font-family: 'Ubuntu Mono';
    margin-top: 30px;
}

.card {
    border-left: none;
    border-right: none;
    border-top: none;
}
</style>
