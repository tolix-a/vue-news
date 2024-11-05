<template lang="">
  <div class="newsItem" v-for="(item,index) in articles" :key="index">
    <div @click="goToUrl(item.content_url)">
      <img :src="item.image_url"/>
      <h2>{{item.title}}</h2>
      <div>{{item.publisher}}<span>{{item.published_at}}</span></div>
      <p>{{item.summary}}</p>
    </div>
  </div>
</template>
<script>
export default {
  props:{
    articles:{
      type: Array,
      Required: true,
    }
  },
  methods: {
    goToUrl(url) {
      // window.location.href = url; // 해당 URL로 이동
      window.open(url, '_blank');
    }
  }
}
</script>
<style lang="scss">
  .newsItem{
    position: relative;
    padding-bottom: 20px;
    &::after{
      content: '';
      position: absolute; /* 상자 안에 위치를 조정 */
      left: 0;
      bottom: 0;
      width: 100%;
      border-bottom: 1px solid rgb(207, 207, 207); /* 테두리 추가 */
      pointer-events: none;
    }
    >div{
      cursor: pointer;
      img{
        width:100%;
        height: 250px;
        object-fit: cover;
      }
      h2{
        font-size: 21px;
        font-weight: 700;
        padding-top: 20px;
        line-height: 1.3;
      }
      h2,p{
        text-align: left;
      }
      >div{
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 5px 0 20px;
        font-size: 14px;
        color: #7c7c7c;
      }
      p{
        line-height: 1.3;
      }
    }
  }

</style>