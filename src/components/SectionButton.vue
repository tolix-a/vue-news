<template lang="">
  <div class="sectionButton">
    <button 
      v-for="(category, index) in categories"
      :key="index"
      :class="{ active: activeCategory === category.value }"
      @click="setActiveCategory(category.value)">
      {{ category.label }}
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeCategory: 'politics',
      categories: [
        { label: '정치', value: 'politics' },
        { label: '경제', value: 'economy' },
        { label: '사회', value: 'society' },
        { label: '문화', value: 'culture' },
        { label: '세계', value: 'world' },
        { label: '기술', value: 'tech' },
        { label: '연예', value: 'entertainment' },
        { label: '논평', value: 'opinion' }
      ]
    };
  },
  mounted(){
    this.$emit('fetch', this.activeCategory);
    //페이지에 들어가면 기본값 값이 넘어가게
  },
  methods: {
    setActiveCategory(value) {
      this.activeCategory = value;
      this.fetchCategoryData(value);
    },
    fetchCategoryData(value) {
      // 부모 컴포넌트에 이벤트를 발생시켜서 데이터 fetching 요청
      this.$emit('fetch', value); 
      //fetch는 함수 명. 뒤에 있는 애(value)는 부모한테 보낼 값,, value 말고도 2개든 3개든 더 써도 됨.
      //articleview.vue파일 async fetchData(category) { 여기로 들어옴 category = 여기다 쓴 value
      //('fetch', value, aa, bb) 라고 썼다면 async fetchData(category, f, x) 라고 쓰면 다 들어옴 emit에 쓴거랑 개수가 맞아야 오류가 안 남


      console.log(`Fetching data for ${value}`);
    }
  },
}
</script>

<style lang="scss">
  .sectionButton{
    width: 100%;
    display: flex;
    overflow-x:auto;
    white-space: nowrap;
    justify-content: space-between;
    // justify-content: center;
    gap: 5px;
    margin-bottom: 20px;
    // margin-top: 5px;

    button{
      border: none;
      border-radius: 10%;
      cursor: pointer;
      padding: 6px 13px;
      &.active{
        background-color: #42b983; // 활성화된 버튼의 색상
        color: white; // 텍스트 색상
      }
    }
  }

</style>