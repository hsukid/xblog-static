<template>
  <Layout>
    <article class="uk-article">
      <h1 class="uk-article-title">{{ article.title }}</h1>
      <p class="uk-article-meta">{{ day(article.updated_at) }}</p>
      <p class="uk-text-lead">{{ article.brief }}</p>

      <div v-html="html(article.content)"></div>
    </article>
  </Layout>
</template>

<page-query>
  query {
    allStrapiArticle (
      sortBy: "id:DESC"
      limit: 1
    ) {
      edges {
        node {
          id
          title
          content
          brief,
          updated_at
        }
      }
    }
  }
</page-query>

<script>
import Markdown from 'markdown-it'
const md = new Markdown()
export default {
  name: 'Home',
  computed: {
    article() {
      return this.$page.allStrapiArticle.edges[0].node
    }
  },
  methods: {
    html(str) {
      return md.render(str)
    }
  }
}
</script>

<style></style>
