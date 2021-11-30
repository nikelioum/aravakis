<template>
    <div>
    <h1>hello</h1>
    <p>{{mountain}}</p>
    <p>User id - {{$route.params.id}}</p>
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
        `https://wordpress-534216-2279478.cloudwaysapps.com/wp-json/wp/v2/articles/${$route.params.id}?author=1?_fields=acf&acf_format=standard`
      ).then(res => res.json())
    }

}
</script>