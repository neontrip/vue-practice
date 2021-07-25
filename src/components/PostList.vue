<template>
  <div class="post" v-for="post in posts" :key="post.id">
    <div><strong>Название:</strong> {{ post.title }}</div>
    <div><strong>Описание:</strong> {{ post.body }}</div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "PostList",
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
});
</script>

<style scoped lang="sass">
.post
  padding: 20px
  border: white 2px solid
  border-radius: 3px
  margin: 10px 10px
  background-color: azure
  -webkit-box-shadow: 4px 4px 8px 0 rgba(34, 60, 80, 0.2)
  -moz-box-shadow: 4px 4px 8px 0 rgba(34, 60, 80, 0.2)
  box-shadow: 4px 4px 8px 0 rgba(34, 60, 80, 0.2)
</style>
