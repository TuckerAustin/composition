<template>
  <div class="home">
    <h1>Homepage</h1>
    <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">toggle posts</button>
    <button @click="posts.pop()">delete a post</button>
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import { ref } from "vue";
export default {
  name: "Home",
  components: { PostList },
  setup() {
    const posts = ref([
      {
        title: "welcome to the blog",
        body:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        id: 1,
      },
      { title: "top 5 CSS tips", body: "lorem ipsum", id: 2 },
    ]);
    const showPosts = ref(true);

    return { posts, showPosts };
  },
};
</script>
