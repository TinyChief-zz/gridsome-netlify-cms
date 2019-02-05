<template>
  <Layout>
    <h2>Latest blog posts</h2>
    <ul>
      <li
        v-for="edge in $page.allBlogPost.edges"
        :key="edge.node._id">
        {{ edge.node.title }}
        <a :href="edge.node.path">Перейти</a>
      </li>
    </ul>
  </Layout>
</template>

<page-query>
query getAll {
  allBlogPost {
    edges {
      node {
        title
        path
      }
    }
  }
}
</page-query>
