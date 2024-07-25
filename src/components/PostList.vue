<template>
  <div class="post" v-for="post in posts">
    <div><b>Название:</b> {{ post.title }}</div>
    <div><b>Описание:</b> {{ post.body }}</div>
  </div>
</template>

<script>
export default {
  props: {
    posts: {
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
</style>
