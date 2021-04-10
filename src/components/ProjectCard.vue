<template>
  <div
    class="uk-card uk-card-default uk-card-body uk-card uk-card-hover uk-card-small"
  >
    <div class="uk-card-title uk-flex uk-flex-between">
      <g-link class="uk-link-heading" :to="`/article/${item.id}`">
        <span class="uk-margin-small-right" uk-icon="icon: github" />
        {{ item.name }}
      </g-link>
      <g-link class="uk-link-heading" :to="`/article/${item.id}`">
        <span class="uk-margin-small-right" uk-icon="icon: arrow-left" />
        前往
      </g-link>
    </div>
    <hr class="uk-divider-icon" />
    <p>
      {{ item.brief }}
    </p>
    <div class="uk-card-footer uk-flex uk-flex-right">
      <template v-for="tag in item.tags">
        <span :class="['uk-label', labels[tag.color]]" :key="tag.id">{{
          tag.name
        }}</span>
      </template>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectCard',
  props: {
    item: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      labels: {
        red: 'uk-label-danger',
        yellow: 'uk-label-warning'
      }
    }
  }
}
</script>

<style scoped>
.uk-card {
  position: relative;
}
.uk-card-title {
  position: relative;
}
.uk-card-body > span {
  font-size: 12px;
}
.uk-card-body > p {
  margin-top: 10px;
}
.uk-card-footer span {
  margin-left: 10px;
}
</style>
