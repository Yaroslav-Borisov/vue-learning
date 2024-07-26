<template>
  <form class="creating-form" @submit.prevent>
    <h3>Создание поста</h3>
    <input
      v-model="newPost.title"
      class="creating-form__input"
      type="text"
      placeholder="Название"
    />
    <input v-model="newPost.body" class="creating-form__input" type="text" placeholder="Описание" />
    <button class="creating-form__button" @click="onNewPostCreation">Создать</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      newPost: {
        title: '',
        body: '',
      },
    };
  },
  methods: {
    onNewPostCreation() {
      this.newPost.id = Date.now();
      this.$emit('createPost', this.newPost);
      this.newPost = {
        title: '',
        body: '',
      };
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
