<template lang="">
  <div class="home">
    <h2>뉴스</h2>
    <MainArticle/>
  </div>
</template>
<script>
import MainArticle from '@/components/MainArticle';

export default {
  name: 'HomeView',
  computed:{ //마운팅이 실행되기 전에 중괄호 안에 있는 내용을 실행
    
  }, 
  components: {
    MainArticle
  }
}
</script>
<style lang="scss">
  .home{
    width: 100%;
    padding: 0 20px;
    box-sizing: border-box;
  }
</style>