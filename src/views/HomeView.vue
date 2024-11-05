<template lang="">
  <div class="home">
    <div v-if="loading">로딩 중...</div>
    <div v-else>
    <!-- 데이터 표시 -->
    </div>
    <div class="up">
      <p><span>▲</span>뉴욕 증시, 혼조세 출발… 호실적 테슬라 17% 급등</p>
    </div>
    <MainArticle/>
    <MainSmall/>
    <MainArticle/>
    <MainSmall/>
    <MainArticle/>
    <MainSmall/>
  </div>
</template>
<script>
import MainArticle from '@/components/MainArticle';
import MainSmall from '@/components/MainSmall';
import axios from 'axios';

export default {
  name: 'HomeView',
  data() {
    return {
      news: {
        economy: [],
        politics: [],
        society: [],
        culture: []
      },
      loading: true
    }
  },
  components: {
    MainArticle,MainSmall
  },
  async created() {
    try {
      const response = await axios.get('http://localhost:4000/news'); // 서버 주소
      console.log(response.data);
      this.news = response.data;
    } catch (error) {
      console.error('데이터 로딩 중 오류 발생:', error);
    } finally {
      this.loading = false;
    }
  },
}
</script>
<style lang="scss">
  .home{
    width: 100%;
    padding: 0 20px;
    box-sizing: border-box;
    .up{
      width: 100%;
      background-color: #42b983;
      height: 40px;
      border-radius: 10px;
      margin-bottom: 20px;

      display: flex;
      align-items: center;
      justify-content: center;
      p{
        max-width: 360px;
        color: white;
        span{
          padding-right: 10px;
        }
      }
    }
  }
</style>