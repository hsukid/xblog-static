<template>
  <Layout>
    <div class="uk-text-center" uk-grid>
      <template v-for="item in socials">
        <SocialCard :key="item.id" :item="item.node" />
      </template>
    </div>
  </Layout>
</template>
<page-query>
  query {
    allStrapiSocial {
      totalCount
      edges {
        node {
          id
          name
          url
          cover
        }
      }
    }
  }
  </page-query>
<script>
import SocialCard from '~/components/SocialCard'
export default {
  name: 'SocialPage',
  components: { SocialCard },
  computed: {
    socials() {
      return this.$page.allStrapiSocial.edges || []
    }
  }
}
</script>

<style></style>
