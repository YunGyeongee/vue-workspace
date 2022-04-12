<template> <!-- HTML -->
  

  <Modal :onerooms="onerooms" :click="click"/>

  <!-- 상단 Nav 메뉴 만들기 -->
  <div class="menu"> 
    <a v-for="작명 in menubar" :key="작명">{{ 작명 }}</a>
  </div>

  <Discount />

  <Card :room="onerooms[0]" />
  <Card :room="onerooms[1]" />
  <Card :room="onerooms[2]" />
  <Card :room="onerooms[3]" />
  <Card :room="onerooms[4]" />
  <Card :room="onerooms[5]" />

</template>

<script> // JS
// document.getElementById().innerHTML = ??

// var array = [10, 20, 30];
// array[0];

import data from './assets/oneroom.js'; // 확장자 생략해도 됨
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import Card from './Card.vue';

export default {
  name: 'App',
  data(){ // 데이터 보관함
    return { // object 자료료 저장하기 -> {자료이름 : 자료내용}
      Object : {name : 'kim', age : 20},
      모달창 : false,
      click : 0,
      신고수 : [0, 0, 0],
      price1 : 60,
      price2 : 70,
      스타일 : 'color : blue',
      menubar : ['Home', 'Shop', 'About'],
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
      onerooms : data,
    }
  },
  method : { // 함수 만들기
    increase(){
      this.신고수 += 1; // 함수안에서 데이터 쓸 땐 this.데이터명 으로 기재-> this를 안붙인다면 is not defined 에러가 뜸
    },
  },

  components: {
    Discount : Discount, // Discount 로 한 문자로 생략가능함
    Modal : Modal,
    Card : Card,
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
