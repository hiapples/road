<script setup>
import { ref, onMounted } from 'vue';


const activeButton = ref('one');
const activePage = ref('one'); // 用來儲存目前顯示的頁面

const latitude = ref(null);//緯度
const longitude = ref(null);//經度
const errorMessage = ref('');

//取得用戶當前位置
const getUserLocation = () => {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(
      (position) => {
        latitude.value = position.coords.latitude;
        longitude.value = position.coords.longitude;
      },
      (error) => {
        errorMessage.value = '請允許存取位置或開啟 GPS';
      }
    );
  } else {
    errorMessage.value = '您的瀏覽器不支援定位功能';
  }
};
// 當元件掛載時自動取得位置
onMounted(() => {
  getUserLocation();
});


const clickOne = () => {
  activeButton.value = 'one';
  activePage.value = 'one'; // 顯示 page1
};

const clickThree = () => {
  activeButton.value = 'three';
  activePage.value = 'three'; // 顯示 page2
};



</script>

<template>
  <div class="container-fluid button-back">
    <div class="row">
      <div class="button col-6 d-flex justify-content-center font2" :class="{ active: activeButton === 'one' }"@click="clickOne">國道一號</div>
      <div class="button col-6 d-flex justify-content-center font2" :class="{ active: activeButton === 'three' }"@click="clickThree">國道三號</div>
    </div>
  </div>
  <div v-if="activePage === 'one'" class="container-fluid page1 mt-2">
    <div class="row" >
      <div class="col-12 d-flex justify-content-center font mt-2">中壢服務區</div>
      <div class="col-12 d-flex justify-content-center font mt">湖口服務區</div>
      <div class="col-12 d-flex justify-content-center font mt">泰安服務區</div>
      <div class="col-12 d-flex justify-content-center font mt">西螺服務區</div>
      <div class="col-12 d-flex justify-content-center font mt">新營服務區</div>
      <div class="col-12 d-flex justify-content-center font mt">仁德服務區</div>
    </div>
  </div>

  <div v-if="activePage === 'three'" class="container-fluid page2 mt-2">
    <div class="row">
      <p v-if="errorMessage">{{ errorMessage }}</p>
      <p v-else-if="latitude && longitude">緯度: {{ latitude }}, 經度: {{ longitude }}</p>
      <div class="col-12 d-flex justify-content-center font mt-2"><a href="https://www.google.com.tw/maps/place/%E9%97%9C%E8%A5%BF%E6%9C%8D%E5%8B%99%E5%8D%80/@24.8011082,121.1898685,17z/data=!3m2!4b1!5s0x34683ebdbe57f375:0xd0735f997f005528!4m6!3m5!1s0x3468394000000001:0xe6a8cc38096ec213!8m2!3d24.8011034!4d121.1924434!16s%2Fg%2F155rzm1n?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDIwOS4wIKXMDSoASAFQAw%3D%3D">關西服務區</a></div>
      <div class="col-12 d-flex justify-content-center font mt">西湖服務區</div>
      <div class="col-12 d-flex justify-content-center font mt">清水服務區</div>
      <div class="col-12 d-flex justify-content-center font mt">南投服務區</div>
      <div class="col-12 d-flex justify-content-center font mt">古坑服務區</div>
      <div class="col-12 d-flex justify-content-center font mt">東山服務區</div>
      <div class="col-12 d-flex justify-content-center font mt">關廟服務區</div>
    </div>
  </div>
</template>

<style scoped>
html, body {
  height: 100%;
  margin: 0;
  overflow: hidden; /* 禁止滾動 */
  -webkit-overflow-scrolling: touch; /* 適用於觸控滾動 */
  touch-action: none; /* 禁止觸控操作 */
  -webkit-touch-callout: none; /* 禁止長按操作 */
}
a{
  color: black;
  text-decoration: none;
}
.button-back {
  background-color: #b0afaf;
}
.button {
  background-color: #b0afaf;
  padding: 40px 10px 40px 10px;
  cursor: pointer;
}
.active {
  background-color: #4b4b4b;
  color: white;
}
.page1, .page2 {
  overflow-y: hidden;
}
.font {
  font-size:42px;
}
.font2{
  font-size:24px;
}
.mt { 
  margin-top: 30px !important;
}
</style>
