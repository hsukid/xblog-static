<template>
  <div class="side-bar uk-card uk-card-default uk-card-small">
    <!-- <div class="uk-card-body"> -->
    <!-- <div class="side-bar-item">
        <g-link to="/">最新动态</g-link>
      </div>
      <div class="side-bar-item">
        <g-link to="/social">社交圈</g-link>
      </div>
      <div class="side-bar-item">
        <g-link to="/blogs">博客列表</g-link>
      </div>
      <div class="side-bar-item">
        <g-link to="/projects">开源项目</g-link>
      </div> -->
    <ul class="uk-card-body uk-nav-default uk-nav-parent-icon" uk-nav>
      <li :class="[{ 'uk-active': path === '/' }]">
        <g-link to="/">
          <span class="uk-margin-small-right" uk-icon="icon: star" />
          最新动态
        </g-link>
      </li>
      <li :class="[{ 'uk-active': path === '/social' }]">
        <g-link to="/social">
          <span class="uk-margin-small-right" uk-icon="icon: phone" />
          社交圈
        </g-link>
      </li>
      <li :class="[{ 'uk-active': path === '/blogs' }]">
        <g-link to="/blogs">
          <span class="uk-margin-small-right" uk-icon="icon: list" />
          博客列表
        </g-link>
      </li>
      <li :class="[{ 'uk-active': path === '/projects' }]">
        <g-link to="/projects">
          <span class="uk-margin-small-right" uk-icon="icon: github" />
          开源项目
        </g-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'SideBar',
  computed: {
    path() {
      return this.$route.path
    }
  }
}
</script>

<style scoped>
.side-bar {
  width: 200px;
  margin-right: 20px;
}
.uk-nav > li > a {
  display: flex;
  padding: 20px;
}
.uk-nav-default > li.uk-active > a {
  font-weight: bold;
}
</style>
