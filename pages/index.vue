<template>
  <div class="app flex flex-col justify-between">
    <!-- header component -->
    <div class="headerSite">
      <Header/>
    </div>
    <!-- content page-->
    <div class="content flex flex-col items-center justify-between">
      <!-- images -->
      <div class="title flex justify-center  w-full ">
        <VueSlickCarousel v-if="screen > 610" class="VueSlickCarousel mb-12" :arrows="false"  :autoplay="true" :speed="900"  :autoplaySpeed="5000" :dots="false">
          <nuxt-link to="./market"><img  src="../assets/images/img-slyd/slyd1.jpg" alt="خوراکی"></nuxt-link>
          <nuxt-link to="./market"><img  src="../assets/images/img-slyd/slyd2.jpg" alt="صنعتی"></nuxt-link>
          <nuxt-link to="./market"><img  src="../assets/images/img-slyd/slyd8.gif" alt="جانبی"></nuxt-link>
          <nuxt-link to="./market"><img  src="../assets/images/img-slyd/slyd4.jpg" alt="خانگی"></nuxt-link>
          <nuxt-link to="./market"><img  src="../assets/images/img-slyd/slyd5.jpg" alt="جانبی"></nuxt-link>
          <nuxt-link to="./market"><img  src="../assets/images/img-slyd/slyd6.jpg" alt="جانبی"></nuxt-link>
          <nuxt-link to="./market"><img  src="../assets/images/img-slyd/slyd7.jpg" alt="جانبی"></nuxt-link>
          <nuxt-link to="./market"><img  src="../assets/images/img-slyd/slyd3.jpg" alt="جانبی"></nuxt-link>
        </VueSlickCarousel>
        <VueSlickCarousel v-if="screen <= 610" class="VueSlickCarousel mb-12" :arrows="false"  :autoplay="true" :speed="900"  :autoplaySpeed="5000" :dots="false">
          <nuxt-link to="./market"><img  src="../assets/images/img-slyd/slyd-small1.jpg" alt="جانبی"></nuxt-link>
          <nuxt-link to="./market"><img  src="../assets/images/img-slyd/slyd-small2.jpg" alt="جانبی"></nuxt-link>
          <nuxt-link to="./market"><img  src="../assets/images/img-slyd/slyd-small3.jpg" alt="جانبی"></nuxt-link>
          <nuxt-link to="./market"><img  src="../assets/images/img-slyd/slyd-small4.jpg" alt="جانبی"></nuxt-link>
          <nuxt-link to="./market"><img  src="../assets/images/img-slyd/slyd-small5.jpg" alt="جانبی"></nuxt-link>
        </VueSlickCarousel>
      </div>
      <!-- items for option in site -->
      <div class="items w-full flex justify-evenly  mb-12">
        <div v-for="item in items" class="flex flex-col items-center imgitem ">
          <a href="#"><img :src="require(`./../assets/images/items/${item.number}.png`)"  alt="img" width="55"></a>
          <p class="text-s">{{item.text}}</p>
        </div>
      </div>
      <!-- 2 image-->
      <div class="images flex justify-evenly mb-12">
        <img src="../assets/images/next-items1.jpg" class=" m-1 rounded-lg" alt="">
        <img src="../assets/images/next-items2.jpg" class=" m-1 rounded-lg" alt="">
      </div>
      <!-- off text to center -->
      <h3 class="text-title flex items-center"><i class="bi bi-percent text-red-600 font-bold"></i>سایت ما با تخفیفات و جشنواره های فراوان در خدمت مشتریان خود میباشد<i class="bi bi-percent text-red-600 font-bold"></i></h3>
       <!-- 4 products -->
       <div style="background-color: #941b80; border: 5px solid #941b80" class="overproducts flex justify-between mb-12 mt-12">
        <div class="flex flex-col items-center justify-center logoProduct">
          <img src="https://www.digikala.com/statics/img/svg/digiplus-logo.svg" width="100"  alt="">
          <img src="../assets/images/plus-widget.png" width="135" alt="">
        </div>
        <div class="product flex justify-between">
           <div v-for="item in overItems" class="flex flex-col items-center justify-around">
             <img :src="require(`../assets/product-img/${item.img}.jpg`)" style="width: 100%;" alt="">
             <h4>{{item.qemat}} تومان </h4>
           </div>
        </div>
      </div>
      <!-- last image -->
      <img src="../assets/images/ferst-small-img.jpg" v-if="screen <= 824 " class="rounded-md mb-12" style="width: 96%;" alt="">
      <img src="../assets/images/ferst-img.jpg" v-if="screen > 824" class="rounded-md mb-12" style="width: 96%;" alt="">
      <!-- market grup -->
      <div class="grups flex flex-col items-center justify-evenly mb-12">
          <grups title="جانبی" text="انواع لوزم جانبی با کیفیت را از ما با بهترین قیمت ممکن بخرید! لوازم های جانبی ما تمامی از برند های اورجینال و اصلی تهیه میشوند تا مشتریان بتوانند با خیال راحت از ما خرید بکنند." img="1" addres="janbe"/>
          <grups title="خانگی" text="اسایش را در خانه با محصولات ما افزایش دهید!  لوازم های جانبی ما تمامی از برند های اورجینال و اصلی تهیه میشوند تا مشتریان بتوانند با خیال راحت از ما خرید بکنند." img="2" addres="xange"/>
          <grups title="صنعتی" text="کار خود را توسعه دهید با لوارم اصلی از سایت ما!  لوازم های جانبی ما تمامی از برند های اورجینال و اصلی تهیه میشوند تا مشتریان بتوانند با خیال راحت از ما خرید بکنند." img="3" addres="sanate"/>
          <grups title="خوراکی" text="خوراکی های سالم و خوشمزه و تازه را از این سایت تهیه کنید تا پرورش عالی را تجربه کنید!  لوازم های جانبی ما تمامی از برند های اورجینال و اصلی تهیه میشوند تا مشتریان بتوانند با خیال راحت از ما خرید بکنند." img="4" addres="xorake"/>
      </div>
      <br>
      <!-- 4 image -->
      <div class="imgs flex justify-around items-center mb-12">
        <img src="../assets/images/4img/img1.jpg" alt="">
        <img src="../assets/images/4img/img2.jpg" alt="">
        <img src="../assets/images/4img/img3.jpg" alt="">
        <img src="../assets/images/4img/img4.jpg" alt="">
      </div>
      <!-- 4 products -->
       <div class="overproducts flex justify-between mb-12">
        <div class="flex flex-col items-center justify-center logoProduct">
          <img src="https://www.digikala.com/statics/img/svg/amazing-typo.svg" width="100"  alt="">
          <img src="../assets/images/General.png" width="100" alt="">
        </div>
        <div class="product flex justify-between">
           <div v-for="item in overItems2"  class="flex flex-col items-center justify-around">
             <img :src="require(`../assets/product-img/${item.img}.jpg`)" style="width: 100%;" alt="">
             <h4>{{item.qemat}} تومان </h4>
           </div>
        </div>
      </div>
      <!-- download apps -->
      <div class="apps flex justify-between items-center p-4  mb-12">
        <div class="flex items-center log">
          <img src="../assets/images/download-logo.png" class="logo"  alt="">
          <h3 class="m-0 mr-2" style="color: white">دانلود اپلیکیشن</h3>
        </div>
        <!-- download for 4 divais -->
        <div class="flex download">
          <img src="https://www.digikala.com/statics/img/svg/appStores/google-play.svg" class="m-2" alt="">
          <img src="https://www.digikala.com/statics/img/svg/appStores/coffe-bazzar.svg" class="m-2" alt="">
          <img src="https://www.digikala.com/statics/img/svg/appStores/myket.svg" class="m-2" alt="">
          <img src="https://www.digikala.com/statics/img/svg/appStores/sib-app.svg" class="m-2" alt="">
        </div>
      </div>
      <!-- last image -->
      <img src="../assets/images/last-small-img.jpg" v-if="screen <= 824 " class="rounded-md mb-12" style="width: 96%;" alt="">
      <img src="../assets/images/last-img.jpg" v-if="screen > 824" class="rounded-md mb-12" style="width: 96%;" alt="">
    </div>
    <!-- footer site -->
    <div class="footerSite"><footersite/></div>
  </div>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
import grups from "~/components/grups";
import footersite from "~/components/footer";
import Header from "~/components/header";
export default {
  name: 'home',
  components:{Header, grups,footersite,VueSlickCarousel},
  data(){
    return{
      screen:null,
      // items for option site
      items:[
        {text:'دیجی کالا جت',number:1},
        {text:'دیجی استایل',number:2},
        {text:'دیجی پی',number:3},
        {text:'دیجی کالا مهر',number:4},
        {text:'ماموریت ها',number:5},
        {text:'دیجی پلاس',number:6},
        {text:'دیجی کلاب',number:7},
        {text:'پیندو',number:8}
      ],
      overItems:[
        {img:39,qemat:'۵۷۰,۰۰۰'},
        {img:40,qemat:'۲۹۹,۰۰۰'},
        {img:46,qemat:'۳۷۰,۰۰۰'},
        {img:48,qemat:'۸۹۹,۰۰۰'}
      ],
      overItems2:[
        {img:6,qemat:'۷۰۰,۰۰۰'},
        {img:42,qemat:'۳۱۰,۰۰۰'},
        {img:47,qemat:'۱۹۹,۰۰۰'},
        {img:44,qemat:'۶۵۰,۰۰۰'}
      ]
    }
  },
  // get width size
  mounted() {
       this.screen = window.screen.width
  }
}
</script>
<style scoped>
.app{
  width: 100%;
}
.VueSlickCarousel{
  width: 100%;
}
.images img{
  width: 48%;
}
.imgs img{
  width: 22%;
  border-radius: 10px;
  margin: 10px;
}
.apps{
  background-color: #3c4b6d;
  width: 96%;
  border-radius: 10px;
}
.download img{
  width: 25%;
}
.overproducts{
  width: 96%;
  height: 350px;
  background-color: #ef3a4f;
  border-radius: 10px;
  border: 5px solid #ef3a4f;
}
.logoProduct{
  width: 20%;
}
.product{
  width: 80%;height: 100%;
  background-color: #ffffff;
  border-radius: 10px 0px 0px 10px;
}
@media only screen and (max-width: 890px){
    .apps h3{
      font-size: 12px;
    }
}
@media only screen and (max-width: 824px){
  .items p{
    font-size: 10px;
  }
  .imgitem{
    width: 40px;
  }
  .imgitem p{
    font-size: 6px;
  }
  .imgs{
  flex-wrap: wrap;
  width: 99%;
}
  .imgs img{
    width: 45%;
  }
  .log{
    display: none;
  }
  .download{
    width: 99%;
    justify-content: space-between;
  }
  .download img{
    width: 45%;margin: 20px;
  }
  .text-title{
    font-size: 20px;
  }
  .overproducts{
    flex-direction: column;
  }
  .product{
    width: 100%;
  }
  .logoProduct{
    flex-direction: row;
    width: 100%;
    justify-content: center;
  }
  .product h4{
  font-size: 13px;
 }
}
@media only screen and (max-width: 690px){
    .apps{
      flex-direction: column;
    }
   .download {
     flex-wrap: wrap;
   }
  .log{
    display:flex;
    margin-bottom: 10px;
  }
  .log h3{
    font-size: 20px;
  }
  .text-title{
    font-size: 13px;
  }
  .overproducts{
    height: 299px;
  }
}
@media only screen and (max-width: 500px){
	.overproducts{
    height: 287px;
  }
}
@media only screen and (max-width: 444px){
	.items{
    flex-wrap: wrap;
    margin-top: 10px;
  }
  .imgitem{
    width: 60px;
    margin: 15px;
  }
  .imgitem p{
    font-size: 10px;
  }
  .text-title{
    font-size: 11px;
  }
  .product h4{
  font-size: 11px;
 }
}
@media only screen and (max-width: 400px){
    .images{
      display: flex;
      flex-direction: column;
      align-items: center;
    }
  .images img{
    width: 96%;
  }
	  .imgs img{
      width: 96%;
    }
  .overproducts{
    height: 228px;
  }
}
@media only screen and (max-width: 362px){
   .download img{
     width: 100%;
   }
  .overproducts{
    height: 215px;
  }
  .product h4{
  font-size: 10px;
 }
  .text-title{
    font-size: 8px;
  }
  .logoProduct img{
    width: 50px;
  }
  .logoProduct img{
    width: 50px;
  }
}
</style>
