<template>
  <div class="#app">
    <nav class="bg-mypurple-400">
      <labell for="" class="text-2xl logo">Seravabi</labell>
      <ul class="text-white">
        <li>Score {{ score }} / 10</li>
        <li>10 ข้อ</li>
        <li><a href="#">Exit</a></li>
      </ul>
    </nav>

    <div class="bg-mypurple-200 ing">
      <section class="title_and_index ">
        <div
          class="max-w-3xl overflow-hidden shadow-lg bg-myyellow-100 h-28 w-2/5 ring ring-myyellow-200 ring-offset-0 card-title"
        >
          <div class="px-6 pt-4 pb-2">
            <span
              class="text-3xl inline-block bg-myyellow-200 rounded-full px-3 py-1 text-lg font-semibold text-gray-700 mr-2 mb-2 card-number"
              >{{index+1}}</span
            >
          </div>
          <div class="px-6 py-4">
            <div class="font-bold mb-2 text-4xl text-gray-700">{{datagame[index].question}}</div>
            <p class="text-gray-700 text-base"></p>
          </div>
          <div class="px-6 pt-4 pb-2">
            <span
              class="text-2xl inline-block bg-myyellow-200 rounded-full px-3 py-1 text-lg font-semibold text-gray-700 mr-2 mb-2 card-type"
              >{{datagame[index].type}}</span
            >
          </div>
        </div>
      </section>

      <section class="choose_answer w-full text-myystone-300">
        <div class="choose">
          <button
            class="w-2/5 mx-2 my-2 hover:bg-myyellow-101 focus:ring focus:ring-myyellow-200 h-36 max-w-3xl rounded-tl-3xl overflow-hidden shadow-lg bg-myyellow-100"
            @click="choicechcek1(datagame[index].choice1)">
            <div class="px-6 py-6">
              <div class="font-bold text-3xl mb-2 text-gray-700">{{datagame[index].choice1}}</div>
              <p class="text-gray-700 text-base"></p>
            </div>
          </button>
          <button
            class="w-2/5 mx-2 my-2 hover:bg-myyellow-101 focus:ring focus:ring-myyellow-200 h-36 max-w-3xl overflow-hidden shadow-lg bg-myyellow-100"
            @click="choicechcek2(datagame[index].choice2)" >
            <div class="px-6 py-6">
              <div class="font-bold text-3xl mb-2 text-gray-700">{{datagame[index].choice2}}</div>
              <p class="text-gray-700 text-base"></p>
            </div>
          </button>
        </div>
        <div class="choose">
          <button
            class="w-2/5 mx-2 my-2 hover:bg-myyellow-101 focus:ring focus:ring-myyellow-200 h-36 max-w-3xl overflow-hidden shadow-lg bg-myyellow-100"
            @click="choicechcek3(datagame[index].choice3)" >
            <div class="px-6 py-6">
              <div class="font-bold text-3xl mb-2 text-gray-700">{{datagame[index].choice3}}</div>
              <p class="text-gray-700 text-base"></p>
            </div>
          </button>
          <button
            class="w-2/5 mx-2 my-2 hover:bg-myyellow-101 focus:ring focus:ring-myyellow-200 h-36 max-w-3xl rounded-br-3xl overflow-hidden shadow-lg bg-myyellow-100"
            @click="choicechcek4(datagame[index].choice4)" >
            <div class="px-6 py-6">
              <div class="font-bold text-3xl mb-2 text-gray-700">{{datagame[index].choice4}}</div>
              <p class="text-gray-700 text-base"></p>
            </div>
          </button>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import { datagame } from "../data/word.js";
export default {
  name: "GuessingGame",
  data(){
    return{
      datagame: datagame,
      index: 0,
      score: 0,
    };
  },
  methods:{
    choicechcek1(check){
      this.index++;
      if(check == datagame[this.index-1].answer){
        this.score++;
      }
    },
    choicechcek2(check){
      this.index++;
      if(check == datagame[this.index-1].answer){
        this.score++;
      }
    },
    choicechcek3(check){
      this.index++;
      if(check == datagame[this.index-1].answer){
        this.score++;
      }
    },
    choicechcek4(check){
      this.index++;
      if(check == datagame[this.index-1].answer){
        this.score++;
      }
    }
  },
};
</script>

<style scoped>
/* bodybodybodybodybodybodybodybodybody */
body {
  font-size: 14px;
  color: #000;
  margin: 0;
  padding: 0;
  background-color: #26128a;
}

/* navvvvvvvvvvvvvvvvv */
* {
  padding: 0;
  margin: 0;
  text-decoration: none;
  list-style: none;
  box-sizing: border-box;
  display: inline-block;
}
nav {
  height: 80px;
  width: 100%;
}
labell.logo {
  line-height: 80px;
  padding: 0 50px;
  color: #fff;
}
nav ul {
  float: right;
  margin-right: 60px;
}
nav ul li {
  display: inline-block;
  line-height: 80px;
  margin: 0 50px;
}
nav ul li a {
  color: white;
}

.ing {
  height: calc(100vh - 80px);
  width: 100vw;
  justify-content: center;
}

.title_and_index {
  display: flex;
  justify-content: center;
  margin: 40px;
  padding: 10px;
}

.choose_answer {
  display: flex;
  justify-content: center;
  flex-direction: column;
  
}
.choose {
  display: flex;
  justify-content: center;
}

.card-title {
  border-radius: 0px 24px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.card-number {
  border-radius: 0px 10px;
}
.card-type {
  border-radius: 0px 10px;
}
</style>
