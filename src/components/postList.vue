<template>
 <post-item v-for="post in posts" :key="post.id" :post="post" @remove="$emit('remove', post)"/>
</template>

<script>
import postItem from './postItem.vue'
  export default {
  components: { postItem },
    props: {
      posts: {
        type: Array,
        required: false,
      }
    }
  }
</script>

<style scoped>

</style>