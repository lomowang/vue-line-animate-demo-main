<script setup>
  import { ref } from 'vue'
  const scroll = ref(false)
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
      <li></li>
    </ul>




  </div>
  <header>
  </header>
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
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: darkgray;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    transition: all 0.5s;
  }
  
  .scroll .kvList{
    width: 1200px;
    height: 300px;
  }
</style>
