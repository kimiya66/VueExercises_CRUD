<template>
  <div>
    This is the list of all blogs.
    <div v-for="blog in blogs">
      <h2>{{blog.title}}</h2>
      <article>{{blog.body}}</article>
    </div>
  </div>
</template>

<script>
  export default {

    data () {
      return {
        blogs:[]
      }
    },
    methods: {
    },
    created() {
        this.$http.get('https://jsonplaceholder.typicode.com/posts').then(function (data) {
          this.blogs=data.body.slice(0-10);
        })
      }


  }

</script>

<style>
  body{
    margin: 0;
    font-family: 'Nunito SemiBold';
  }
</style>
