<template lang="">
  <div class="small">
    <h2>'비침습 연속혈당측정기' 개발 기업 아폴론, 중기부 장관상 수상</h2>
    <div>연합뉴스<span>2024-10-24T23:59:00</span></div>
  </div>
</template>
<script>
export default {
  
}
</script>
<style lang="scss">
  .small{
    text-align: left;
    position: relative;
    margin-bottom: 40px;
    padding: 30px 0;

    &::after{
      content: '';
      position: absolute; /* 상자 안에 위치를 조정 */
      left: 0;
      bottom: 0;
      width: 100%;
      border-bottom: 1px solid rgb(226, 226, 226); /* 테두리 추가 */
      pointer-events: none;
    }
    h2{
      font-size: 21px;
      font-weight: 700;
      // padding-top: 20px;
      line-height: 1.3;
    }
    div{
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding-top: 5px;
      font-size: 14px;
      color: #7c7c7c;
    }
  }
</style>