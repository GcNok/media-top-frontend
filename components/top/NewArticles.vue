<template>
  <section class="new-articles-wrapper">
    <SectionTitle
      :title="'新着記事'"
      :comment="'暮らしのアイデアをSS編集部が毎日更新'"
    />
    <ArticleList :type="ARTICLE_TYPE_NEW" :limit="10" />
    <LinkButton :title="'新着記事一覧を見る'" :link="'/contents/latest'" />
  </section>
</template>

<script lang="ts">
import Vue from 'vue'
import ArticleList from '~/components/common/ArticleList.vue'
import LinkButton from '~/components/common/LinkButton.vue'
import SectionTitle from '~/components/top/SectionTitle.vue'
import { ConstArticle } from '~/const/article'

export default Vue.extend({
  name: 'NewArticles',
  components: {
    SectionTitle,
    ArticleList,
    LinkButton
  },
  data() {
    return {
      ARTICLE_TYPE_NEW: ConstArticle.ARTICLE_TYPE_NEW
    }
  }
})
</script>

<style lang="scss" scoped>
.new-articles-wrapper {
  margin-bottom: responsive-height(20);
}
</style>
