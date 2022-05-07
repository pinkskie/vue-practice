<template>
  <form @submit.prevent>
    <input v-model="post.title" class="input" type="text" placeholder="название"/>
    <input v-model="post.body" class="input" type="text" placeholder="тело"/>
    <button @click="createPost">Добавить</button>
  </form>
</template>

<script>
  export default {
    data() {
      return {
        post: {
          title: '',
          body: ''
        }
      }
    },
    methods: {
      createPost() {
        this.post.id = Date.now()
        this.$emit('create', this.post)
        this.post = {
          title: '',
          body: ''
        }
      }
    }
  }
</script>

<style scoped>

</style>