<template>
  <section id="main" class="main-alt">
    <div v-for="post in posts" :key="post.slug" class="blog">
      <div class="blog-title">{{ post.h1 }}</div>
      <div class="blog-introtext">{{ post.description }}</div>
      <div class="blog-tag">{{ post.tags }}</div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
export default {
  async asyncData(ctx) {
    const { data } = await axios.get(`http://127.0.0.1:8000/api/posts/`);
    return {
      posts: data.results,
    }
  }
}
</script>

<style>

</style>


