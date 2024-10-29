<template lang="">
  <!-- <div class="serComponent" v-for="(item,index) in articles" :key="index"> -->
    <figure class="resultb" v-for="(item,index) in srData" :key="index">
      <img :src="item.image_url"/>
      <div>
        <p>{{item.title}}</p>
      </div>
    </figure>
  <!-- </div> -->
</template>
<script>
export default {
  props:{
    srData:{
      type: Array,
      Required: true,
    }
  }
}
</script>
<style lang="scss">
  .resultb{
    display: flex;
    position: relative;
    margin: 0;
    padding-bottom: 18px;

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
      width: 110px;
      margin-right: 15px;
    }
    div{
      p{
        margin: 0;
        text-align: left;
        font-weight: bold;
        font-size: 18px;
        padding-bottom: 5px;
      }
      span{
        font-size: 15px;
      }
    }
  }
</style>