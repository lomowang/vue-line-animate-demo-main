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

<h2 class="banText" >
  <img src="https://img.onl/miZoHD" class="slowLogo">
</h2>
<div class="banner">
    <li class="banner1">coffee</li>
    <li class="banner2">news</li>
    <li class="banner3">about_us</li>
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

<!-- 商品列 -->
<div class="wrap">
  <div class="products">
      <img src="https://picsum.photos/400/300?random=28" class="shop1">
        <!-- 放icon -->
        <div class="icon">
          <img src="https://img.icons8.com/small/16/000000/hearts.png"/>
          <img src="https://img.icons8.com/small/16/000000/add-shopping-cart.png"/>
        </div>
        <!-- <li class="color"></li> -->
          <p class="shopInt">[晚安配方]-喝完可以睡
            <br>250g
            <br class="Price">NT$350元
          </p>
    </div>
  <div class="products">
      <img src="https://picsum.photos/400/300?random=20" class="shop1">
        <!-- 放icon -->
        <div class="icon">
          <img src="https://img.icons8.com/small/16/000000/hearts.png"/>
          <img src="https://img.icons8.com/small/16/000000/add-shopping-cart.png"/>
        </div>
        <!-- <li class="color"></li> -->
          <p class="shopInt">[晚安配方]-喝完可以睡
            <br>250g
            <br class="Price">NT$350元
          </p>
    </div>
  <div class="products">
      <img src="https://picsum.photos/400/300?random=44" class="shop1">
        <!-- 放icon -->
        <div class="icon">
          <img src="https://img.icons8.com/small/16/000000/hearts.png"/>
          <img src="https://img.icons8.com/small/16/000000/add-shopping-cart.png"/>
        </div>
        <!-- <li class="color"></li> -->
          <p class="shopInt">[晚安配方]-喝完可以睡
            <br>250g
            <br class="Price">NT$350元
          </p>
    </div>
  <div class="products">
      <img src="https://picsum.photos/400/300?random=14" class="shop1">
        <!-- 放icon -->
        <div class="icon">
          <img src="https://img.icons8.com/small/16/000000/hearts.png"/>
          <img src="https://img.icons8.com/small/16/000000/add-shopping-cart.png"/>
        </div>
        <!-- <li class="color"></li> -->
          <p class="shopInt">[晚安配方]-喝完可以睡
            <br>250g
            <br class="Price">NT$350元
          </p>
    </div>
</div>
<div class="wrap">
  <div class="products">
      <img src="https://picsum.photos/400/300?random=94" class="shop1">
        <!-- 放icon -->
        <div class="icon">
          <img src="https://img.icons8.com/small/16/000000/hearts.png"/>
          <img src="https://img.icons8.com/small/16/000000/add-shopping-cart.png"/>
        </div>
        <!-- <li class="color"></li> -->
          <p class="shopInt">[晚安配方]-喝完可以睡
            <br>250g
            <br class="Price">NT$350元
          </p>
    </div>
  <div class="products">
      <img src="https://picsum.photos/400/300?random=90" class="shop1">
        <!-- 放icon -->
        <div class="icon">
          <img src="https://img.icons8.com/small/16/000000/hearts.png"/>
          <img src="https://img.icons8.com/small/16/000000/add-shopping-cart.png"/>
        </div>
        <!-- <li class="color"></li> -->
          <p class="shopInt">[晚安配方]-喝完可以睡
            <br>250g
            <br class="Price">NT$350元
          </p>
    </div>
  <div class="products">
      <img src="https://picsum.photos/400/300?random=55" class="shop1">
        <!-- 放icon -->
        <div class="icon">
          <img src="https://img.icons8.com/small/16/000000/hearts.png"/>
          <img src="https://img.icons8.com/small/16/000000/add-shopping-cart.png"/>
        </div>
        <!-- <li class="color"></li> -->
          <p class="shopInt">[晚安配方]-喝完可以睡
            <br>250g
            <br class="Price">NT$350元
          </p>
    </div>
  <div class="products">
      <img src="https://picsum.photos/400/300?random=16" class="shop1">
        <!-- 放icon -->
        <div class="icon">
          <img src="https://img.icons8.com/small/16/000000/hearts.png"/>
          <img src="https://img.icons8.com/small/16/000000/add-shopping-cart.png"/>
        </div>
        <!-- <li class="color"></li> -->
          <p class="shopInt">[晚安配方]-喝完可以睡
            <br>250g
            <br class="Price">NT$350元
          </p>
    </div>
</div>
<!-- footer -->
<div class="footer">
  <ul class="aboutus">關於我們
    <li>品牌介紹</li>
    <li>SlowSpace路漫慢</li>
  </ul>
  <ul class="sever">顧客服務
    <li>聯絡我們</li>
    <li>購物須知</li>
    <li>會員分級</li>
    <li>常見Ｑ＆Ａ</li>
  </ul>
  <ul class="time">營業時間
    <li>週一至週二 18:00-00:00</li>
    <li>週四至週日 18:-00:00</li>
    <li>每週三公休</li>
    <li>地址：900屏東縣屏東市上海路17號</li>
  </ul>
</div>
</template>

<style>
  *{
    margin: 0;
    padding: 0;
    /* font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif; */
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    /* border: 1px solid black; */
  }
  body{
    height: 180vh;
    /* width: 100%; */
  }

  .banner{
    /* position: relative; */
    padding: 50px;
    width: auto;
    display: flex;
    /* left: -400%; */
    /* right: 100px; */
    /* padding-left:  */
    justify-content: center;
    list-style: none;
    font-size: 40px;
  }

  .banner1{
    margin-right: 20px;
  }
  .banner1:hover{
    border-bottom:2px solid black ;
    cursor: pointer;
    opacity: 1;
  }
  
  .banner2{
    margin-right: 20px;
  }
  .banner2:hover{
    border-bottom:2px solid black ;
    cursor: pointer;
    opacity: 1;
  }
  .banner3:hover{
    border-bottom:2px solid black ;
    cursor: pointer;
    opacity: 1;
  }
    
  .banText{
   position: absolute;
   width: 100px;
   height: 100px;
   left: 50px;
   margin-top: 10px;
   border-radius: 100%;

  }
  .slowLogo{
    /* border: 1px solid black; */
    display: flex;
    border-radius: 50%;
    width: 100px;
    height: 100px;
    box-shadow: 10px 5px 30px rgba(173, 169, 169, 0.5);

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
  .wrap{
    position: relative;
    display: inline-flex;
    padding-bottom: 40px;
    /* background-color: #eee; */
    /* border: 1px solid black; */
    width: 100%;
    z-index: 0;
  }
  .products{
    
    margin: 2px;
    padding: 10px;
    
  }
  .icon{
    position: absolute;
    bottom: 15%;
    left: -70px;
    top: 75%;
    z-index: 10;
    justify-content: center;
  }
  /* .color{
    position: absolute;
    background-color: #fff;
    bottom: 15%;
    left: 20%;
    width: 74px;
    height: 20px;
    list-style: none;
  } */
  .shopInt{
    width: auto;
    font-size: 30px;
    font-weight: 800;
  }
  .footer{
    /* width: 100%; */
    display: flex;
    padding-top: 0;
    padding: 80px;
    /* margin: 0px; */
    border: 1px solid black;
    justify-content: center;

    list-style: none;
    /* padding-left: 5px;
    padding-right: 5px; */
    /* margin-right: 10px; */
    height: 100px;
    background-color: rgb(0, 0, 0);
    color: #eee;
    border: 1px solid white;
    padding: 100px;

  }
  .aboutus{
     list-style: none;
     font-size: 20px;
     padding-right: 200px;
  }
  .sever{
     list-style: none;
     font-size: 20px;
     padding-right: 200px;

  }
  .time{
     list-style: none;
     font-size: 20px;
     padding-right: 200px;

  }
  .kv{
    position: relative;
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
