<template>
  <div class="article-type-wrapper">
    <nuxt-link
      v-for="(tab, index) in ARTICLE_TAB_LIST"
      :key="index"
      class="article-type"
      :class="{ selected: tab.type === type }"
      :to="`/contents/${tab.type}`"
      ><span class="article-type-text">{{ tab.title }}</span></nuxt-link
    >
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { ConstArticle } from '~/const/article'
export default Vue.extend({
  name: 'ArticleTab',
  props: {
    type: {
      type: String,
      default: ConstArticle.ARTICLE_TYPE_POPULAR
    }
  },
  data() {
    return {
      ARTICLE_TAB_LIST: ConstArticle.ARTICLE_TAB_LIST
    }
  }
})
</script>

<style lang="scss" scoped>
.article-type-wrapper {
  display: flex;
  overflow-x: scroll;

  .article-type {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: responsive-height(50);
    background: whitesmoke;
    list-style: none;
    border: 1px solid $color-gray;
    text-decoration: none;
    color: unset;
    @include media-query($pc) {
      margin-bottom: 10px;
      height: 50px;
    }

    .article-type-text {
      white-space: nowrap;
    }
  }

  .selected {
    background: white;
    border-top: 3px solid $color-primary-green;
    border-bottom: none;
  }
}
</style>
