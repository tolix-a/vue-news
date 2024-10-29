<template lang="">
  <div class="search">
    <div>
      <p>검색 결과 " <span>{{query.query}}</span> "</p>
      <p class="num"><span>{{sResults.total_items}}</span>개</p>
    </div>
    <section>
      <div v-if="sResults.total_items === 0">검색 결과가 없습니다.</div>
      <SearchArticle :srData="srData"/>
    </section>
  </div>
</template>

<script>
import axios from 'axios';
import SearchArticle from '@/components/SearchArticle'

export default {
  name: 'SearchView',
  data(){
    return {
      sResults: [],
      srData:[]
    };
  },
  components:{
    SearchArticle
  },
  computed: {    //서치에서 검색
    query(){
      return this.$route.query || '';
    }
  },
  created(){
    this.fetchSearch(this.$route.query)
    //서치가 아닌 페이지에서 검색할 때 실행
  },
  watch: { //서치에서 검색
    query: 'fetchSearch'    
  },
  methods: {    
    async fetchSearch({query}){
      const m = 'articles';
      const response = await axios.get(`http://localhost:4000/news/search`, {params: {m, keyword: query}});
      this.sResults = response.data;
      this.srData = response.data.data;
      console.log(response.data);
    }
  }
}
</script>
<style lang="scss">
  .search{
    width: 100%;
    padding: 0 20px;
    box-sizing: border-box;
    >div{
      display: flex;
      justify-content: space-between;
      >p{
        text-align: left;
        font-weight: bold;
        font-size: 18px;
        span{
          color: #42b983;
        }
      }
      .num{
        span{
          padding-right: 5px;
        }
      }
    }
    section{
      display: flex;
      flex-direction: column;
      gap: 18px;
      padding-top: 10px;
      >div{
        padding-top: 50px;
      }
    }
  }
</style>