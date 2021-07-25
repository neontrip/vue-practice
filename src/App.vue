<template>
  <div class="posts-container">
    <PostForm @create="createPost" />
    <PostList :posts="posts" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";

export default defineComponent({
  name: "App",
  components: {
    PostForm,
    PostList,
  },
  data() {
    return {
      posts: [
        { id: 1, title: "JavaScript", body: "Описание поста 1" },
        { id: 2, title: "JavaScript", body: "Описание поста 2" },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
  },
});
</script>

<style lang="sass" scoped>
.posts-container
  margin: 0 auto
  max-width: 50%
</style>
