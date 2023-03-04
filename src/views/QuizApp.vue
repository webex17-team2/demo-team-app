<template>
  <h1 class="quiz">Vue クイズ</h1>
  <div class="app">
    <h2 class="Q">Q. {{ "この子の名前は？" }}</h2>
    <img
      class="quiz-image"
      src="https://th.bing.com/th/id/R.28b2b02e5a0b6d10d0037f65afebe8b8?rik=1Ew%2b2%2bF8o5xoYQ&riu=http%3a%2f%2fblog-imgs-75.fc2.com%2fa%2fn%2fk%2fankosokuho%2fc98f6357.jpg&ehk=%2b5PqrDSG0DHTqOgNC0RJq5%2bT99Hj3Nsy%2fAOLq0aiHY0%3d&risl=&pid=ImgRaw&r=0"
      alt="クイズタイトル"
    />
    <div class="container">
      <div class="box">
        <button v-on:click="ansOne">由比ヶ浜結</button>
        <div v-if="yes" class="ans">正解</div>
      </div>
      <div class="box">
        <button v-on:click="ansTwo">雪ノ下雪乃</button>
        <div v-if="noOne" class="ans">不正解</div>
      </div>
      <div class="box">
        <button v-on:click="ansThree">東山奈央</button>
        <div v-if="noTwo" class="ans">不正解</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      yes: false,
      noOne: false,
      noTwo: false,
    }
  },
  methods: {
    ansOne: function () {
      this.yes = true
    },
    ansTwo: function () {
      this.noOne = true
    },
    ansThree: function () {
      this.noTwo = true
    },
  },
}
</script>

<style>
.app {
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: center;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

.quiz-image {
  height: 300px;
  width: 500px;
  object-fit: contain;
}

.container {
  display: flex;
  height: 2em;
  width: 300px;
  padding: 1em;
  justify-content: space-around;
}

.box {
  padding: 20px;
}

button {
  height: 50px;
  width: 100px;
}

.quiz {
  background-color: black;
  color: white;
  padding-left: 100px;
}
.Q {
  background-color: rgb(3, 156, 148);
  color: white;
  width: 100%;
  text-align: center;
}

.ans {
  color: white;
  background-color: rgb(188, 96, 96);
  font-size: 30px;
  font-weight: bold;
}
</style>
