<template lang="">
  <div class="newsItem" v-for="(item,index) in articles" :key="index">
    <img :src="item.image_url"/>
    <h2>{{item.title}}</h2>
    <p>{{item.summary}}</p>
  </div>
</template>
<script>
export default {
  props:{
    articles:{
      type: Array,
      Required: true,
    }
  }
}
</script>
<style lang="scss">
  .newsItem{
    position: relative;
    // padding-bottom: 18px;
    // margin: 0 10px;
    &::after{
      content: '';
      position: absolute; /* 상자 안에 위치를 조정 */
      left: 0;
      bottom: 0;
      width: 100%;
      border-bottom: 1px solid rgb(207, 207, 207); /* 테두리 추가 */
      pointer-events: none;
    }
    img{
      width:100%;
      height: 250px;
      object-fit: cover;
    }
    h2,p{
      text-align: left;
    }
    p{
      line-height: 1.3;
    }
  }

</style>