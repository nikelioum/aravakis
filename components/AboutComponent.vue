<template>
    <div>

        <div class="container terms">
          <div class="row">
          <div class="col-md-12">
          <nav aria-label="breadcrumb" style="margin-top:100px;">
          <ol class="breadcrumb">
          <li class="breadcrumb-item"><nuxt-link to="/">Αρχική</nuxt-link></li>
          <li class="breadcrumb-item active" aria-current="page">Η Εταιρεία μας</li>
          </ol>
          </nav>
          </div>
          </div>
        </div>

        <div class="container terms-body">
          <p v-if="$fetchState.pending"><Loader/></p>
            <div class="row">
                <div class="col-md-12">
                    <h3>Η Εταιρεία μας</h3>
                </div>
                <div class="col-md-6">
                    <div v-html="mountain.content"></div>
                </div>
                <div class="col-md-6">
                    <img class="img-fluid mb-2" src="~/assets/images/wall1.jpeg">
                    <img class="img-fluid mb-2" src="~/assets/images/wall2.jpg">
                    <img class="img-fluid mb-2" src="~/assets/images/wall3.jpeg">
                </div>
            </div>
        </div>

    </div>
</template>

<script>
export default{

     data() {
      return {
        mountain: []
      }
    },
    async fetch() {
      this.mountain = await fetch(
        'https://wordpress-534216-2279478.cloudwaysapps.com/wp-json/wp/v2/posts/63'
      ).then(res => res.json())
    }

}
</script>

<style scoped>
.terms{
     font-family: 'Ubuntu Mono';
}
.terms-body{
    font-family: 'Ubuntu Mono';
}
</style>
