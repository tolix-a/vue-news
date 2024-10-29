<template lang="">
  <div class="newsItem" @click="goToDetail">
    <img src='../../public/laya-clode.jpg'/>
    <h2>Bowen: Gaza nurse who filmed moments after Israeli strike describes chaos and grief</h2>
    <p>In the video, a paramedic runs panic-stricken between dead and dying civilians in the immediate aftermath of the strike.</p>
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
      this.$router.push('/detail')
    }
  },
}
</script>
<style lang="scss">
  .newsItem{
    position: relative;
    padding-bottom: 10px;
    // margin: 0 10px;
    cursor: pointer;
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