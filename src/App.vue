<template>
  <div class="black-bg" v-if="current_modal == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <span>상세내용임</span>
      <button @click="current_modal = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
  </div>

  <div v-for="(item, i) in oneroom" :key="i">
    <img :src="item.image" alt="" class="room-img" />
    <h4>{{ item.title }}</h4>
    <h5>{{ item.content }}</h5>
    <p>{{ item.price }}원</p>
  </div>
</template>

<script>
import info_oneroom from './assets/oneroom';

export default {
  name: 'App',
  data() {
    return {
      //데이터 보관함.
      //변수 등등.
      //object 자료형으로 {자료이름:자료내용}
      oneroom: info_oneroom,
      alert: [0, 0, 0],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
      menus: ['Home', 'Shop', 'About'],
      price: [50, 60, 70],
      current_modal: false, //false 닫힘, true 열림
    };
  },
  methods: {},
  components: {},
};
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
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
</style>
