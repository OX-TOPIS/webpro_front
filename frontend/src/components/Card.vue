<template>
  <div class="#appp">
    <div class="card-ing1">
      <nav class="bg-mypurple-400">
        <labell for="" class="text-2xl logo">Seravabi</labell>
        <ul class="text-white">
          <li>Score {{ score_knew }} / 10</li>
          <li>10 ข้อ</li>
          <li><a href="#">Exit</a></li>
        </ul>
      </nav>
    </div>
    <!-- All card -->
    <div class="card-ing2">
      <swiper
        :slidesPerView="3"
        :spaceBetween="30"
        :navigation="true"
        :modules="modules"
        class="mySwiper"
      >
        <!-- card -->
        <!-- <swiper-slide v-for="index in 10" :key="index" > -->
          <swiper-slide v-for="(items, index) in datagame" :key="index">
          <label >
            <input type="checkbox" />
            <div class="flip-card ">


              <div class="front text-gray-700 relative">
                <h1 class="">
                  <div class="bg-myyellow-200 px-5 in-index">{{ index+1 }}</div>
                </h1>
                <h2>{{items.question}}</h2>
                <b class="">
                  <span class="bg-myyellow-200 px-3 py-2 in-type ">{{items.type}}</span>
                </b>
                <p class="click inset-x-0 bottom-0 ">Tap to see definition</p>
              </div>


              <div class="back front text-gray-700 relative">
                <h1 class="">
                  <div class="bg-myyellow-200 px-5 in-index">{{ index+1 }}</div>
                </h1>
                <h2>{{items.answer}}</h2>
                <b></b>
                <div class="click">
                  <div class="back-buttom">Tap to see definition</div>
                  <button class="button back-button-r" @click="score_count2(index)">
                  didn't know it
                  </button>
                  <button class="button back-button-l" @click="score_count1(index)">
                  knew it
                  </button>
                  
                  
                  
                </div>
                
              </div>

              
            </div>
          </label>
        </swiper-slide>
        <!-- Card Finish -->
        <swiper-slide>
          <label>
            <div class="flip-card">
              <div class="front">
                <h1>Finish</h1>
              </div>
            </div>
          </label>
        </swiper-slide>
      </swiper>
    </div>
    <!-- <p>score_knew: {{ score_knew }} score_dontknew: {{ score_dontknew }}</p> -->
  </div>
</template>
<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";

import "swiper/css/pagination";
import "swiper/css/navigation";

import "./style.css";

// import required modules
import { Pagination, Navigation } from "swiper";
import { datagame } from "../data/word.js";
export default {
  data() {
    return {
      score_knew: 0,
      score_dontknew: 0,
      indexcheck: [],
      indexcheck2: [],
      datagame: datagame,
    };
  },
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Pagination, Navigation],
    };
  },
  methods: {
    score_count1(index) {
      if (
        !this.indexcheck.includes(index) &&
        !this.indexcheck2.includes(index)
      ) {
        this.indexcheck.push(index);
        this.score_knew += 1;
      }
    },
    score_count2(index) {
      if (
        !this.indexcheck.includes(index) &&
        !this.indexcheck2.includes(index)
      ) {
        this.indexcheck2.push(index);
        this.score_dontknew += 1;
      }
    },
  },
};
</script>
