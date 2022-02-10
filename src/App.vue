<script setup>
  import { ref } from 'vue'
  const scroll = ref(false)
  // 跑輪播圖
  const total = ref(5)
  // 跑動畫時間
  const animationDuration = 10
  
  // 輪播圖效果
  const img = function(n){
    return {
      backgroundImage:`url(https://picsum.photos/1920/1200?random=${n})`,
      animationDuration:`${animationDuration}s`,
      animationDelay:`${(n-1)*animationDuration/2}s`
    }
  }
   

  // 監聽整個視窗滑動的樣子
  window.addEventListener('scroll',function(){
    // 當滑動的Ｙ軸值大過0將會執行畫面縮放 
    scroll.value = (window.scrollY > 0)
  })


</script>

<template>
  <div class="kv" :class="{scroll}">
    <!-- 輪播效應 -->
    <ul class="kvList">
      <!-- 輪播圖綁定 -->
      <li v-for="n in total" :style="img(n)"></li>
    </ul>
  </div>


</template>

<style>
  *{
    margin: 0;
    padding: 0;
  }
  body{
    height: 200vh;
  }
  .kv{
    position: relative;
    width: 100vw;
    height: 100vh;
    background-color: rgb(113, 167, 162);
    
  }
  /* 輪播定位 */
  .kvList{
    list-style: none;
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: darkgray;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    transition: all 0.5s;
  }
  
  .kvList > li{
    position: absolute;
    width: 100%;
    height: 100%;
    background-position: center;
    background-repeat: no-repeat;
    background-size: 150% auto;
  }

  .kvList > li{
    animation-name: kvAnimate;
    animation-timing-function: linear;
    animation-iteration-count: infinite;

  }

  .scroll .kvList{
    width: 1200px;
    height: 300px;
  }

  @keyframes kvAnimate {
    0%{
      opacity: 0;
      background-size: 150% auto;
    }
    25%{
      opacity: 1;
    }
    50%{
      opacity: 1;
    }
    75%{
      opacity: 0;
    }
    to{
      opacity: 0;
      background-size: 120% auto;
    }
  }
</style>
