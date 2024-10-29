<template>
  <div class="main">
    <div class="head">
      <router-link to="/">News.</router-link>
      <div class="headbutton">
        <nav>
          <router-link to="/article">국내</router-link>
          <router-link to="/global">해외</router-link>
        </nav>
        <button @click="toggleSearch"></button>
      </div>
    </div>
    <div class="searchBox" v-if="isVisible">
      <form @submit.prevent="onSearch">
        <button type="submit"></button>
        <input type="text" v-model="searchQuery" placeholder="검색"/>
      </form>
    </div>
    <router-view/>
    <div class="footer">
      <p>Copyrightⓒ News. 2024 All Rights Reserved</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isVisible: false,
      searchQuery: ''
    };
  },
  methods: {
    toggleSearch(){
      this.isVisible = !this.isVisible;
    },
    onSearch(){
      if (this.searchQuery){
        this.$router.push({
          path: '/search',
          query: {query:this.searchQuery}
        });
      }
    }
  },
  watch: {
    // 다른페이지로 가면 검색 닫기
    '$route'() {
      this.isVisible = false;
      this.searchQuery = '';
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  max-width: 480px;
  height: 100vh;
  margin: 0 auto;
}

a{
  text-decoration: none;
}

.main {
  box-sizing: border-box;
  .head{
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: white;

    width: 100%;
    padding: 10px 20px;
    box-sizing: border-box;
    >a {
      font-size: 32px;
      font-weight: bold;
      color: #42b983;
      &.router-link-exact-active {
        color: #42b983;
      }
    }
    .headbutton{
      display: flex;
      gap: 15px;
      nav{
        display: flex;
        gap: 10px;
        a{
          font-size: 17px;
          font-weight: 600;
          color: #2c3e50;
          &.router-link-exact-active {
          color: #42b983;
          }
        }
      }
      button{
        width: 26px;
        height: 26px; 
        background: url('../public/search-outline.svg');
        border: none;
        cursor: pointer;
      }
    }
  }
  .searchBox{
    height: 55px;
    // background-color: white;
    // background-color: #EBEBEB;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 99;

    width: 100%;
    padding: 0 20px;
    box-sizing: border-box;
    form{
      display: flex;
      width: 100%;
      height: 42px;
      // background-color: #EBEBEB;
      background-color: white;
      // border-radius: 20px;
      align-items: center;
      box-sizing: border-box;
      padding: 0 16px;
      border-bottom: 1px solid black;
      
      button{
        width: 26px;
        height: 26px; 
        border: none;
        cursor: pointer;
        background: url('../public/search-outline.svg');
        margin-right: 10px;
      }
      input{
        width: 80%;
        height: 26px;
        text-align: center;
        border: none;
        font-size: 18px;
        background-color: transparent;
      }
    }
  }
  .footer{
    width: 100%;
    padding: 0 20px;
    box-sizing: border-box;

    height: 90px;
    background-color: #EBEBEB;
    margin-top: 30px;
    display: flex;
    justify-content: center;
    align-items:last baseline;

    bottom: 0; /* 화면의 아래쪽에 위치 */
  left: 0;
    p{

    }
  }
  
}
</style>
