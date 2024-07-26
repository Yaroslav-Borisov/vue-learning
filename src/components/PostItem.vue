<template>
  <div class="post">
    <div class="post__data">
      <div><b>Название:</b> {{ post.title }}</div>
      <div><b>Описание:</b> {{ post.body }}</div>
    </div>
    <div class="post__buttons">
      <Button @click="$emit('deletePost', post)">Удалить</Button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      required: true,
    },
  },
};
</script>

<style scoped>
.post {
  margin-bottom: 15px;
  padding: 15px;
  font-family: Arial, Helvetica, sans-serif;
  border: 2px solid #000000;
}

.post__data {
  margin-bottom: 10px;
}

.post__buttons {
  display: flex;
  gap: 10px;
}
</style>
