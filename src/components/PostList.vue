<template>
  <div class="posts" v-if="posts.length > 0">
    <h3>Список постов</h3>
    <PostItem
      v-for="post in posts"
      :post="post"
      :key="post.id"
      @deletePost="$emit('deletePost', post)"
    />
  </div>
  <h3 v-else>Список постов пуст</h3>
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
}
</style>
