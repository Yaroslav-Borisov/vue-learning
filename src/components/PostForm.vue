<template>
  <form class="creating-form" @submit.prevent>
    <h3>Создание поста</h3>
    <input
      v-bind:value="newPost.title"
      @change="onNewPostTitleChange"
      class="creating-form__input"
      type="text"
      placeholder="Название"
    />
    <input
      v-bind:value="newPost.body"
      @change="onNewPostBodyChange"
      class="creating-form__input"
      type="text"
      placeholder="Описание"
    />
    <button class="creating-form__button" @click="onNewPostCreation">Создать</button>
  </form>
</template>

<script>
export default {
  props: {
    createPost: {
      required: true,
    },
  },
  data() {
    return {
      newPost: {
        title: '',
        body: '',
      },
    };
  },
  methods: {
    onNewPostTitleChange(event) {
      console.log(event.target.value);
      this.newPost.title = event.target.value;
    },
    onNewPostBodyChange(event) {
      this.newPost.body = event.target.value;
    },
    onNewPostCreation() {
      this.createPost(this.newPost.title, this.newPost.body);
      this.newPost.title = '';
      this.newPost.body = '';
    },
  },
};
</script>

<style scoped>
.creating-form {
  display: flex;
  flex-direction: column;
  gap: 10px;
  max-width: 300px;
  margin-bottom: 10px;
  font-family: Arial, Helvetica, sans-serif;
}

.creating-form__input {
  padding: 5px;
  border-radius: 3px;
}

.creating-form__button {
  margin: 0;
  padding: 10px;
  font-weight: 700;
  background: none;
  border: 2px solid #000000;
  cursor: pointer;
}
</style>
