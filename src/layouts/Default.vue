<template>
  <div class="layout">
    <header class="header">
      <div class="blog-title">
        <h1>对影行觞</h1>
        <p>欢迎来到对影行觞的个人博客</p>
      </div>
      <!-- <nav class="nav">
        <g-link class="nav__link" to="/">Home</g-link>
        <g-link class="nav__link" to="/about/">About</g-link>
      </nav> -->
    </header>
    <main class="main">
      <SideBar />
      <div class="uk-width-expand uk-card uk-card-default uk-card-small">
        <div class="uk-card-body"><slot /></div>
      </div>
    </main>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>
<script>
import SideBar from '~/components/SideBar.vue'
export default {
  name: 'Layout',
  components: { SideBar }
}
</script>
<style>
body {
  font-family: -apple-system, system-ui, BlinkMacSystemFont, 'Segoe UI', Roboto,
    'Helvetica Neue', Arial, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
}

.layout {
}

.header {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
  height: 350px;
  background-image: linear-gradient(to left, #85d4d4, #3ec18a);
}

.header .blog-title h1 {
  color: #fff;
  font-weight: bold;
}
.header .blog-title p {
  color: #fff;
}

.main {
  display: flex;
  max-width: 1024px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
  justify-content: space-between;
}

.nav__link {
  margin-left: 20px;
}
</style>
