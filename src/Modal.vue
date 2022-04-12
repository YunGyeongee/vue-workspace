<template>
  <div class="black-bg" v-if="모달창 == true">
    <div class="white-bg">
      <img :src="onerooms[click].image" style="width:100%">
      <h4>{{ onerooms[click].title }}</h4>
      <h4>{{ onerooms[click].content }}</h4>
      <h4>{{ onerooms[click].price }}원</h4>
      <button>닫기</button>
    </div>
  </div>
</template>

<script>
export default {
    name : 'Modal-a',
    props : {
        onerooms : Object, // 디버깅용으로 자료형을 틀리게 적어도 오류는 발생하지 않음
        click : Number,
        모달창 : Boolean,
    },
    data() {
        return {

        }
    },
}
</script>

<style>

</style>