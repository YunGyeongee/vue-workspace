<template> <!-- HTML -->
  
  
  <div class="black-bg" v-if="모달창 == true">
    <div class="white-bg">
      <h4>상세 페이지</h4>
      <p>상세페이지 내용입니다.</p>
      <button @click="모달창 == false">닫기</button>
    </div>
  </div>


  
  <!-- 상단 Nav 메뉴 만들기 -->
  <div class="menu"> 
    <a v-for="작명 in menubar" :key="작명">{{ 작명 }}</a>
  </div>

  <!-- js에 있는 데이터 HTML에 꽂아넣고 싶으면 {{ 데이터이름 }} 사용 -->
  <div>
    <img src="./assets/room0.jpg" class="room-img">
    <h4 class="red" :style="스타일" @click="모달창 = true">{{ products[0] }}</h4>
    <p>{{ price1 }}만원</p> 
    <button @click="신고수[0]++">허위매물신고</button> <span>신고수 : {{ 신고수[0] }}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4>{{ products[1] }}</h4>
    <p>{{ price2 }}만원</p>
    <button @click="신고수[1] += 1">허위매물신고</button> <span>신고수 : {{ 신고수[1] }}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4>{{ products[2] }}</h4>
    <p>{{ price2 }}만원</p>
    <button @click="신고수[2] += 1">허위매물신고</button> <span>신고수 : {{ 신고수[2] }}</span>
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
      모달창 : false,
      신고수 : [0, 0, 0],
      price1 : 60,
      price2 : 70,
      스타일 : 'color : blue',
      menubar : ['Home', 'Shop', 'About'],
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
    }
  },
  method : { // 함수 만들기
    increase(){
      this.신고수 += 1; // 함수안에서 데이터 쓸 땐 this.데이터명 으로 기재-> this를 안붙인다면 is not defined 에러가 뜸
    },
  },

  components: {
  }
}
</script>

<style> /* css */
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: raba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

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

.room-img {
  width: 100%;
  margin-top: 40px;
}
</style>
