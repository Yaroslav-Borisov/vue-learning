<template>
  <div class="posts">
    <h3>Список постов</h3>
    <PostItem v-for="post in posts" :post="post" />
  </div>
</template>

<script>
import PostItem from './PostItem.vue';

export default {
  components: {
    PostItem,
  },
  props: {
    posts: {
      required: true,
    },
  },
};
</script>

<style scoped>
.posts {
  display: flex;
  flex-direction: column;
  gap: 10px;
  font-family: Arial, Helvetica, sans-serif;
}
</style>
