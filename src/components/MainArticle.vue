<template lang="">
  <div class="mainItem" @click="goToDetail">
    <img src='../../public/laya-clode.jpg'/>
    <h2>뉴욕 증시, 혼조세 출발… 호실적 테슬라 17% 급등</h2>
    <div>연합뉴스<span>2024-10-24T23:59:00</span></div>
    <p>연일 상승하던 미국 국채 금리가 소폭 하락세를 보이는 가운데, 뉴욕증시가 24일(현지시각) 혼조세로 출발했다. 미국 국채 금리는 이날 소폭 하락세를 보이고 있다. 미국 10년 만기 국채 금리는 4.203%, 20년 만기 국채 금리는 4.568% 수준이다.</p>
  </div>
</template>
<script>
export default {
  props:{
    articles:{
      // type: Array,
      Required: true,
    }
  },
  methods: {
    goToDetail(){
      // this.$router.push('/detail')
    }
  },
}
</script>
<style lang="scss">
  .mainItem{
    position: relative;
    padding-bottom: 30px;
    // margin: 0 10px;
    cursor: pointer;
    &::after{
      content: '';
      position: absolute; /* 상자 안에 위치를 조정 */
      left: 0;
      bottom: 0;
      width: 100%;
      border-bottom: 1px solid rgb(226, 226, 226); /* 테두리 추가 */
      pointer-events: none;
    }
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
      // font-size: 16px;
      // padding-bottom: 10px;
      // color: black;
    }
  }


</style>