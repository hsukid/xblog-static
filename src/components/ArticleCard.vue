<template>
  <div
    class="uk-card uk-card-default uk-card-body uk-card uk-card-hover uk-card-small"
  >
    <g-link class="uk-card-title uk-link-heading" :to="`/article/${item.id}`">
      <span class="uk-margin-small-right" uk-icon="icon: file-edit" />
      {{ item.title }}
    </g-link>
    <span>最近更新 {{ day(item.updated_at) }}</span>
    <p>
      {{ item.brief }}
    </p>
  </div>
</template>

<script>
export default {
  name: 'ArticleCard',
  props: {
    item: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.uk-card {
  position: relative;
}
.uk-card-title {
  display: block;
  position: relative;
  padding-bottom: 10px;
}
.uk-card-title:before {
  position: absolute;
  bottom: 0;
  left: -20px;
  right: -20px;
  content: ' ';
  height: 1px;
  background-color: #eee;
}
.uk-card-body > span {
  font-size: 12px;
}
.uk-card-body > p {
  margin-top: 10px;
}
</style>
