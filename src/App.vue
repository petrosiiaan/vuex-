<template>
  <div id="app">
    <h1>Posts: {{ postsCount }}</h1>
    <PostForm />
    <div class="post" v-for="post in allPosts" :key="post.id">
      <h2>{{ post.title }}</h2>
      <p>{{ post.body }}</p>
    </div>
  </div>
</template>

<script>
import PostForm from './components/PostForm'
import {mapGetters, mapActions} from 'vuex'
export default {
  computed: mapGetters(['allPosts', 'postsCount']),
  methods: mapActions(['getBackend']),
  async mounted() {
    // this.$store.dispatch('getBackend')
    this.getBackend(10)
  },
  components: {
    PostForm
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 60px auto;
}

.post {
  margin-top: 50px;
  padding: 20px;
  border: 1px solid #ccc;
  display: flex;

  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
