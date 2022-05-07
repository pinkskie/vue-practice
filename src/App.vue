<template>
  <post-form @create="createPost"/>
  <post-list :posts="posts" @remove="removePost"/>
</template>

<script>
import PostForm from './components/postForm.vue';
import PostList from './components/postList.vue';

export default {
  name: 'App',
  components: {
    PostForm,
    PostList
    
  },
  data() {
    return {
      posts: [
        {id:1, title: 'js1', body: 'ok'},
        {id:2, title: 'js2', body: 'ok'},
        {id:3, title: 'js3', body: 'ok'},
        {id:4, title: 'js4', body: 'ok'},
      ],
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
    }
  }
}
</script>

<style>
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
li {
  list-style: none;
}
form {
  display: flex;
  gap: 2rem;
  justify-content: center;
}
.input {
  font-size: 1.5rem;
}
</style>
