<template>
  <Layout>
    <div class="article-list">
      <template v-for="project in projects">
        <ProjectCard
          class="article-list-item"
          :key="project.id"
          :item="project.node"
        />
      </template>
    </div>
  </Layout>
</template>

<page-query>
query {
  data: allStrapiProject {
    totalCount
    edges {
      node {
        id
        name
        brief
        url
        tags {
          name
          color
        }
      }
    }
  }
}
</page-query>

<script>
import ProjectCard from '~/components/ProjectCard.vue'
export default {
  name: 'ProjectList',
  components: {
    ProjectCard
  },
  metaInfo: {
    title: '项目列表'
  },
  computed: {
    projects() {
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
