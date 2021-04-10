<template>
  <div class="social-item uk-width-1-3">
    <div class="uk-card uk-card-default uk-card-body uk-card uk-card-hover">
      <g-link class="uk-link-heading" :to="item.url">
        <span class="uk-margin-small-right" uk-icon="icon: star" />
        {{ item.name }}
      </g-link>
      <div class="cover-img">
        <img src="https://avatars.githubusercontent.com/u/9087275?v=4" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SocialCard',
  props: {
    item: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.cover-img {
  width: 100%;
  height: 200px;
  background-position: center center;
  background-size: contain;
}
</style>
