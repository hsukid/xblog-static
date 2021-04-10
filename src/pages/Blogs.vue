<template>
  <Layout>
    <div class="article-list">
      <template v-for="article in articles">
        <ArticleCard
          class="article-list-item"
          :key="article.id"
          :item="article.node"
        />
      </template>
    </div>
  </Layout>
</template>

<page-query>
query {
  data: allStrapiArticle {
    totalCount
    edges {
      node {
        id
        title
        brief
        updated_at
      }
    }
  }
}
</page-query>

<script>
import ArticleCard from '~/components/ArticleCard.vue'
export default {
  name: 'ArticleList',
  components: {
    ArticleCard
  },
  metaInfo: {
    title: '文章列表'
  },
  computed: {
    articles() {
      return this.$page.data.edges || []
    }
  }
}
</script>

<style scoped>
.article-list-item + .article-list-item {
  margin-top: 20px;
}
</style>
