<template>
  <div class="article">
    <SectionButton @fetch="fetchData"/>
    <div class="gap">
      <NewsArticle :articles="articles"/>
    </div>
  </div>
</template>

<script>
import NewsArticle from '@/components/NewsArticle';
import SectionButton from '@/components/SectionButton';
import axios from 'axios';

export default {
  name: 'ArticleView',
  data(){
    return {
      articles: [],
    };
  },
  components: {
    NewsArticle,SectionButton
  },
  methods: {
    async fetchData(category) {
      const m = 'articles';
      const response = await axios.get(`express-server-sand.vercel.app/articles`,  {params: { m, s: category }});
      console.log(response.data.data);
      this.articles = response.data.data;
    }
  },
}
</script>

<style lang="scss">
  .article{
    width: 100%;
    padding: 0 20px;
    box-sizing: border-box;
    
    align-items: left;
    padding-top: 5px;
    >.gap{
      display: flex;
      flex-direction: column;
      gap: 20px;
    }
  }
</style>