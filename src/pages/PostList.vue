<template>
  <div class="post">
    <div v-for="(post,ind) in posts" :key="ind">
      <Post :post="post"/>
    </div>
  </div>

</template>

<script>
  import {defineComponent} from 'vue';
  import axios from 'axios'
  import Post from "../components/Post";

  export default defineComponent({
    name: 'PostList',
    components: {
      Post
    },
    data() {
      return {
        posts: []
      }
    },

    mounted() {
      axios('https://jsonplaceholder.typicode.com/posts')
        .then((response) => {
          this.posts = response.data
        })
        .catch(error => console.log(error))
    }
  })
</script>
