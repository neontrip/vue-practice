<template>
  <div class="form">
    <form class="form__container" @submit.prevent>
      <div class="form__header">
        <h1 class="form__title">Добавить пост:</h1>
        <button class="button form__button" @click="create">Добавить</button>
      </div>
      <input
        v-model="post.title"
        class="input form__input"
        placeholder="Название"
      />
      <textarea
        v-model="post.body"
        class="input form__textarea"
        placeholder="Введите текст"
      />
    </form>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "PostForm",
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    create() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
});
</script>

<style scoped lang="sass">
.form
  margin: 10px 10px
  &__container
    display: flex
    flex-direction: column
    padding: 20px
    background-color: #73899a
    border: #73899a 2px solid
    border-radius: 3px
    -webkit-box-shadow: 4px 4px 8px 0 rgba(34, 60, 80, 0.2)
    -moz-box-shadow: 4px 4px 8px 0 rgba(34, 60, 80, 0.2)
    box-shadow: 4px 4px 8px 0 rgba(34, 60, 80, 0.2)
  &__header
    display: flex
    flex-direction: row
    justify-content: space-between
    align-items: center
    margin-bottom: 10px
  &__title
    font-size: 1.8rem
    letter-spacing: 0.02em
    color: #f8f8f8
  &__button
    align-self: flex-end
  &__input, &__textarea
    border-radius: 5px
    resize: none

.input
  padding: 15px 10px
  font-family: 'PT Sans', sans-serif
  border: white 1px solid
  outline: none
  margin-bottom: 15px
.button
  padding: 10px 10px
  font-family: 'PT Sans', sans-serif
  font-style: normal
  font-weight: bold
  text-transform: uppercase
  background-color: azure
  border-radius: 5px
  border: white 1px solid
  &:hover
    cursor: pointer
</style>
