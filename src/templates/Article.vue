<template>
  <Layout>
    <article class="uk-article">
      <h1 class="uk-article-title">{{ $page.article.title }}</h1>
      <p class="uk-article-meta">{{ $page.article.updated_at }}</p>
      <p class="uk-text-lead">{{ $page.article.brief }}</p>

      <div v-html="html($page.article.content)"></div>
    </article>
  </Layout>
</template>

<page-query>
  query ($id: ID!) {
    article: strapiArticle(id: $id) {
      id
      title
      content
      brief,
      updated_at
    }
  }
</page-query>

<script>
import Markdown from 'markdown-it'

const md = new Markdown()
export default {
  name: 'Article',
  methods: {
    html(str) {
      return md.render(str)
    }
  }
}
</script>

<style></style>
