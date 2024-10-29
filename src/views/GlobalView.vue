<template lang="">
  <div class="global">
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
  name: 'GlobalView',
  data(){
    return {
      articles: [],
    }
  },
  components: {
    NewsArticle,SectionButton
  },
  methods: {
    async fetchData(m, s) {
      this.activeCategory = s; // 활성 카테고리 업데이트
      try {
        const response = await axios.get(`https://api-v2.deepsearch.com/v1/${m}/${s}?&date_from=2024-09-25&date_to=2024-10-24&api_key=43e5844102154529a82e5bd27b43d2ca`);
        this.articles = response.data; // 기사 데이터를 articles 배열에 저장
      } catch (error) {
        console.error('API 요청 중 오류 발생:', error);
      }
    }
  }
}
</script>

<style lang="scss">
  .global{
    width: 100%;
    padding: 0 20px;
    box-sizing: border-box;
    
    align-items: left;
    padding-top: 5px;
    >.gap{
      display: flex;
      flex-direction: column;
      gap: 18px;
    }
  }
</style>