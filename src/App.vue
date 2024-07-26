<template>
  <div>
    <PostForm @createPost="createPost" />
    <PostList :posts="posts" />
  </div>
</template>

<script>
import PostForm from './components/PostForm';
import PostList from './components/PostList';

export default {
  components: {
    PostList,
    PostForm,
  },
  data() {
    return {
      posts: [
        {
          id: 1,
          title: 'Пост о JS',
          body: 'Джава скрипт - это универсальный язык программирования',
        },
        {
          id: 2,
          title: 'Пост о JS 2',
          body: 'Джава скрипт - это универсальный язык программирования 2',
        },
        {
          id: 3,
          title: 'Пост о JS 3',
          body: 'Джава скрипт - это универсальный язык программирования 3',
        },
      ],
    };
  },
  methods: {
    createPost(newPost) {
      this.posts = [...this.posts, newPost];
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
