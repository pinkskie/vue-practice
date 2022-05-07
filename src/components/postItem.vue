<template>
  <div style="display: flex; justify-content: center; gap: 2rem;margin-top: 2rem">
    <li>Название: {{post.title}} , тело: {{post.body}}</li>
    <button @click="$emit('remove', post)">Удалить</button>
  </div>
</template>

<script>
  export default {
    props: {
      post: {
        type: Object,
        required: true,
      }
    }
  }
</script>

<style scoped>

</style>