<template>
  <Layout>
    <h1>{{$page.blogPost.title}}</h1>
    <div class="post-body" v-html="$page.blogPost.content"/>
  </Layout>
</template>

<page-query>
query getOne($path: String!) {
  blogPost (path: $path) {
    title
    content
  }
}
</page-query>
<script>
export default {
  metaInfo() {
    return {
      title: this.$page.blogPost.title
    };
  }
};
</script>

<style>
</style>
