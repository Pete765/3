<template>
  <div class="input-text">
    <input class="input"
           placeholder="Введите текст"
           v-model="post.text"/>
    <button class="button" @click="createPost">Отправить</button>
  </div>
</template>
<script>
export default {
  data() {

    return {
      post: {
        text: '',
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post)
      this.post = {
        text: '',
      }
    }
  }
}
</script>
<style>
.input-text {
  width: 250px;
  display: grid;
}
.input {
  padding: 20px 20px;
  width: 350px;
}
</style>