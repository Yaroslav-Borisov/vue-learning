<template>
  <form class="creating-form" @submit.prevent>
    <h3>Создание поста</h3>
    <Input v-model:value="newPost.title" type="text" placeholder="Название" />
    <Input v-model:value="newPost.body" type="text" placeholder="Описание" />
    <Button class="creating-form__button" @click="onNewPostCreation">Создать</Button>
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
</style>
