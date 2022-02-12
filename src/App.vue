<script setup>
  import { ref } from 'vue'
  const scroll = ref(false)
  // 跑輪播圖
  const total = ref(5)
  // 跑動畫時間
  const animationDuration = 5
  // const pic =("https://lh3.googleusercontent.com/Fn6ICyCIJKig-eCByJifxEgTce5idSCgA-CoJFjnIuukMgVeTjGWAgGz_JqPjL2AbbBYoApnzAHq-q8G1xknD3ATU6oeyIYse4Xtaye_pZNOPxadZ7lp3mZCCaAscoX2PJR7Q3tk6xka5taXCFK10j34ItnTY_9NTg6GkFKSbvjYmb-h2EcArQoOwrMLsMITRgreuK14fvpz7xAXzNmtrwOCM-0yC8nv-GJPiOzsmlxEiNlTcLcICeAVGRGMdVmARQrt5NNbnesRJOKenMnFw12mzBw5nRuw2Vg7AIuK2tGoSrNFjQZJ6Uy3aBIXg_L5KCgH9k_heN8PoWG5aKnLLM9VSrhhBIGzwE6HFp3lM_ixV-1zqPZt17t9juDrWeiBTr0ubACPPIcrLkHVbqvszrmZJwwnooGLxwU1AV39KGr9j6fjGfILQ09_gxEOXWrCWRQ_UAqumFlxVvpk7c1wnuHNSMFhNvfG7Y9Eo46z4MiDMlwgBlTFZttCqv-CSBJTqfDz1CbiyBMbmpkU0hHwAPG1p4F2yqW0hOxUiU6raxcBO2J6z1hkLeBBb1i3EZpoWi57AOlr-Zj8hc6yOmRv8RiUjapx7DNxr7aAvJf72hWKdADjO9ccVNEDlwtayQ6PNs9nhOTkAyN0Qzs3_HgMJu_8X2WtJONINTt9SHYOZtswK0v2k3CQgcOjfR0jyt9h--3wGuxRZ5ECRThwuh17N78=w870-h868-no?authuser=0")

  // 輪播圖效果
  const img = function(n){
    return {
      backgroundImage:`url(https://lh3.googleusercontent.com/HJxXj4T-L_R2_imLWB-c7KEWvAhLJOxbXmAODV7sS_entvp76IWUYMF5LZChIKy7K5vjHcS4DkHMl5pxKdR9KOMUJbaD4ecikCZ1OCcMzJgdnOIOhyTrNEqsR7_e2gRJPhGPnuaNS4Q7iMlEqOno-qZ0fD2gitFeUT2y7sWgkExNK7-iVq8N3UvvqcZaSrrNTeWyILX3r3jCA4y7nY7kPnSYSWkgcTrSyi0cUW8WIAP-K3WNgnBLME2HE0V1HUjsGSOOerTev0PJaZ_jO1gankfpcdUdYPY9Q-no1TVUwbCl5sAQYWyZcGXEtmkO7fW5IXgU847aZjzgJ0-uyyESfs7PRGzMpZbB499cXwynyleGM6WMP-PLempFoiyMAXQXH2u9yrJS3plCcb2pbLayhHCMD6y9Uj3rXkEKhuZJWV2ELHv2r9SqnJhsNYg1Yb4FZfDCDelk26AGV2c3H1rRZ-KZNa3r7bU4iZ28AHAP_ySImNvCdKbB5qH18baiwVv-CYnWx5b5D6beX2kHZRc5jQdu9_uLwoxEGFOq-AFEjNXByLqhyHbgDHB3az2JpttU63qmx7qXdB66UwB8ZUMbJnEX1JB4PlKEfPx96fHKYQ7XvpxyVAxsmSs3rZBNk_HhSKmAbAkld-nzeUp2fJKYMTcTbbw1un5VmuZ9GQAhcooFSoJ27IBuWeCSZPwkKfkj6LeZtixGD96UfpZR8ZC8wAk=w1147-h861-no?authuser=0${n})`,
      animationDuration:`${animationDuration}s`,
      animationDelay:`${(n-1)*animationDuration/2}s`
    }
  }
   

// https://picsum.photos/1920/1200?random=
  // 監聽整個視窗滑動的樣子
  window.addEventListener('scroll',function(){
    // 當滑動的Ｙ軸值大過0將會執行畫面縮放 
    scroll.value = (window.scrollY > 0)
  })


</script>

<template>

<!-- banner -->
<h2 class="banText">SlowSpace</h2>
<div class="banner">
    <h2 class="banner1">coffee</h2>
    <h2 class="banner2">news</h2>
    <h2 class="banner3">about_us</h2>
</div>
  <!-- 上半部 -->
  <div class="kv" :class="{scroll}">
    <!-- 輪播效應 -->
    <ul class="kvList">
      <!-- 輪播圖綁定 -->
      <li v-for="n in total" :style="img(n)"></li>
      <li class="slow">SlowSpace 路漫慢</li>
    </ul>
    <ul class="solwText">
      <li class="slowSlogn1">A Night Space In Pingtung</li>
      <li class="slowSlogn2">將喜愛的品牌帶進熟悉的地方。儘管身在南國，也能互相分享來自各世界各地的咖啡豆，享用專業烘焙工作室的甜點。每一次的合作都是一場驚喜，來場選品探險吧！</li>
    </ul>
      <!-- <li class="slowText"> A Night Space In Pingtung</li> -->
  </div>
<!-- 中間 -->
  <div class="int">
    <ul>
      <li>這邊</li>
      <li>這邊</li>
      <li>這邊</li>
      <li>這邊</li>
    </ul>




  </div>

  


</template>

<style>
  *{
    margin: 0;
    padding: 0;
    /* font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif; */
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  }
  body{
    height: 200vh;
  }

  

  .banner{
    position: relative;
    /* border: 1px solid black; */
    padding: 20px;
    width: auto;
    display: flex;
    left: 40%;
    
    /* justify-content: space-around; */
    /* letter-spacing: 2px */
  }

  .banner1{
    margin-right: 10px;
  }
  .banner2{
    margin-right: 10px;
  }



  .banText{
   /* border: 1px solid black; */
   position: absolute;
   padding: 20px;
   line-height: 30px;
   letter-spacing: 2px;
   /* display: flex;
   flex-direction: column;
   justify-content: center; */
  }


  
  .slow{
    font-size: 80px;
    top: 60%;
    color: aliceblue;
    /* box-shadow: 0px 0px 35px rgba(0,0,0,0.5); */
    /* position: absolute; */
    z-index: 2;
  }
  .slowSlogn1,.slowSlogn2{
    
    display: flex;
    justify-content: center;
    align-items: center;    
    z-index: 0;
    /* p20 */
  }

  .slowSlogn1{
    padding-top: 35%;
    padding-bottom: 0;
    list-style: none;
    font-size: 30px;
    margin-bottom: 20px;
    
  }
  .slowSlogn2{
    font-size: 14px;
    font-weight: 300px;
  }

  .kv{
    position: relative;
    ;
    height: 90vh;
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

  /* 滾輪下滑縮放 */
  .scroll .kvList{
    width: 1200px;
    height: 300px;
    box-shadow: 0px 0px 35px rgba(95, 87, 87, 0.5);
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
