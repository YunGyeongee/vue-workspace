<template> <!-- HTML -->
  <!-- 상단 Nav 메뉴 만들기 -->
  <div class="menu"> 
    <a v-for="작명 in menubar" :key="작명">{{ 작명 }}</a>
  </div>

  <!-- js에 있는 데이터 HTML에 꽂아넣고 싶으면 {{ 데이터이름 }} 사용 -->
  <div>
    <h4 class="red" :style="스타일">{{ products[0] }}</h4>
    <p>{{ price1 }}만원</p> 
  </div>
  <div>
    <h4>{{ products[1] }}</h4>
    <p>{{ price2 }}만원</p>
  </div>
  <div>
    <h4>{{ products[2] }}</h4>
    <p>{{ price2 }}만원</p>
  </div>
</template>

<script> // JS
// document.getElementById().innerHTML = ??

// var array = [10, 20, 30];
// array[0];

export default {
  name: 'App',
  data(){ // 데이터 보관함
    return { // object 자료료 저장하기 -> {자료이름 : 자료내용}
      price1 : 60,
      price2 : 70,
      스타일 : 'color : blue',
      menubar : ['Home', 'Shop', 'About'],
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
    }
  },
  components: {
  }
}
</script>

<style> /* css */
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

</style>
