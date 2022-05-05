<template>
  <div class="post"
       v-for="post in bascetList"
       :key="post.id">
    <div> {{post.text}} </div>
  </div>
</template>
<script>
export default {
  props: {
    bascetList: {
      type: String, Number,
      required: true,
    }
  }
}
</script>
<style>

</style>