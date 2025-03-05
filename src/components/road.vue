<script setup>
import { ref, onMounted } from 'vue';

const activeButton = ref('one');
const activePage = ref('one'); // 控制目前顯示的頁面


// 切換按鈕
const clickOne = () => {
  activeButton.value = 'one';
  activePage.value = 'one';
};

const clickThree = () => {
  activeButton.value = 'three';
  activePage.value = 'three';
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
      <div class="col-12 d-flex justify-content-center font mt-2">
        <a href="https://www.google.com.tw/maps/place/%E4%B8%AD%E5%A3%A2%E6%9C%8D%E5%8B%99%E5%8D%80/@25.0042939,121.2492763,17z/data=!3m1!4b1!4m6!3m5!1s0x346821be57742231:0x7bf3ab53672804a2!8m2!3d25.0042891!4d121.2518512!16s%2Fg%2F155r9l4q?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDMwMi4wIKXMDSoASAFQAw%3D%3D">
          <span>中壢服務區</span>
        </a>
      </div>
      <div class="col-12 d-flex justify-content-center font mt">
        <a href="https://www.google.com.tw/maps/place/%E6%B9%96%E5%8F%A3%E6%9C%8D%E5%8B%99%E5%8D%80+%E5%8C%97%E5%90%91/@24.8609836,121.007205,17z/data=!3m1!4b1!4m6!3m5!1s0x34683135bfa440a5:0x893d9409b7597382!8m2!3d24.8609788!4d121.0120759!16s%2Fg%2F155q2hxs?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDMwMi4wIKXMDSoASAFQAw%3D%3D">
          <span>湖口服務區</span>
        </a>
      </div>
      <div class="col-12 d-flex justify-content-center font mt">
        <a href="https://www.google.com.tw/maps/place/%E6%B3%B0%E5%AE%89%E6%9C%8D%E5%8B%99%E5%8D%80/@24.3289082,120.7142303,17z/data=!3m2!4b1!5s0x3469055489f93871:0x992dbc382c0a959b!4m6!3m5!1s0x3469055511c9ab13:0x5f23c38cc1583053!8m2!3d24.3289033!4d120.7168052!16s%2Fg%2F11c6t92jt7?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDMwMi4wIKXMDSoASAFQAw%3D%3D">
          <span>泰安服務區</span>
        </a>
      </div>
      <div class="col-12 d-flex justify-content-center font mt">
        <a href="https://www.google.com.tw/maps/place/%E8%A5%BF%E8%9E%BA%E6%9C%8D%E5%8B%99%E5%8D%80+%E5%8C%97%E4%B8%8A/@23.7886624,120.4758195,17z/data=!4m6!3m5!1s0x346eb42d95f3e181:0x7a58d76d96564f1!8m2!3d23.7885532!4d120.4794235!16s%2Fg%2F11bbrjgh3z?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDMwMi4wIKXMDSoASAFQAw%3D%3D">
          <span>西螺服務區</span>
        </a>
      </div>
      <div class="col-12 d-flex justify-content-center font mt">
        <a href="https://www.google.com.tw/maps/place/%E6%96%B0%E7%87%9F%E6%9C%8D%E5%8B%99%E5%8D%80+%E5%8C%97%E5%90%91/@23.3395705,120.3078719,17z/data=!3m1!4b1!4m6!3m5!1s0x346e85a588808e71:0xbb93357e00232e56!8m2!3d23.3395656!4d120.3127428!16s%2Fg%2F155q6lvx?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDMwMi4wIKXMDSoASAFQAw%3D%3D">
          <span>新營服務區</span>
        </a>
      </div>
      <div class="col-12 d-flex justify-content-center font mt">
        <a href="https://www.google.com.tw/maps/place/%E4%BB%81%E5%BE%B7%E6%9C%8D%E5%8B%99%E5%8D%80+%E5%8D%97%E4%B8%8B/@22.9059611,120.2602006,17z/data=!3m1!4b1!4m6!3m5!1s0x346e7368e4d37d4f:0xc6920674817516ae!8m2!3d22.9059562!4d120.2650715!16s%2Fg%2F155q85yv?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDMwMi4wIKXMDSoASAFQAw%3D%3D">
          <span>仁德服務區</span>
        </a>
      </div>
    </div>
  </div>

  <div v-if="activePage === 'three'" class="container-fluid page2 mt-2">
    <div class="row">
      <div class="col-12 d-flex justify-content-center font mt-2">
        <a href="https://www.google.com.tw/maps/place/%E9%97%9C%E8%A5%BF%E6%9C%8D%E5%8B%99%E5%8D%80/@24.8011082,121.1898685,17z/data=!3m2!4b1!5s0x34683ebdbe57f375:0xd0735f997f005528!4m6!3m5!1s0x3468394000000001:0xe6a8cc38096ec213!8m2!3d24.8011034!4d121.1924434!16s%2Fg%2F155rzm1n?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDIwOS4wIKXMDSoASAFQAw%3D%3D">
          <span>關西服務區</span>
        </a>
      </div>
      <div class="col-12 d-flex justify-content-center font mt">
        <a href="https://www.google.com.tw/maps/place/%E8%A5%BF%E6%B9%96%E6%9C%8D%E5%8B%99%E5%8D%80/@24.5650371,120.7582243,17z/data=!3m1!4b1!4m6!3m5!1s0x3469a92908285b93:0x390f4ae6014a0bd0!8m2!3d24.5650322!4d120.7607992!16s%2Fg%2F155skv09?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDMwMi4wIKXMDSoASAFQAw%3D%3D">
          <span>西湖服務區</span>
        </a>
      </div>
      <div class="col-12 d-flex justify-content-center font mt">
        <a href="https://www.google.com.tw/maps/place/%E6%B8%85%E6%B0%B4%E6%9C%8D%E5%8B%99%E5%8D%80/@24.2812291,120.5987964,17z/data=!3m1!4b1!4m6!3m5!1s0x346913ecf69b99bf:0x961430d5c3397117!8m2!3d24.2812242!4d120.6013713!16s%2Fg%2F155sgwzc?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDMwMi4wIKXMDSoASAFQAw%3D%3D">
          <span>清水服務區</span>
        </a>
      </div>
      <div class="col-12 d-flex justify-content-center font mt">        
        <a href="https://www.google.com.tw/maps/place/%E5%8D%97%E6%8A%95%E6%9C%8D%E5%8B%99%E5%8D%80/@23.8998685,120.7088229,17z/data=!3m1!4b1!4m6!3m5!1s0x346931f909c92b0d:0xce991d07c3f880a2!8m2!3d23.8998636!4d120.7113978!16s%2Fg%2F1q63cjv6n?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDMwMi4wIKXMDSoASAFQAw%3D%3D">
          <span>南投服務區</span>
        </a>
      </div>
      <div class="col-12 d-flex justify-content-center font mt">
        <a href="https://www.google.com.tw/maps/place/%E5%8F%A4%E5%9D%91%E6%9C%8D%E5%8B%99%E5%8D%80/@23.6084226,120.5419719,17z/data=!3m1!4b1!4m6!3m5!1s0x346ec75a41688cf9:0x3daade3891d1f8fe!8m2!3d23.6084177!4d120.5445468!16s%2Fg%2F155q8jtg?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDMwMi4wIKXMDSoASAFQAw%3D%3D">
          <span>古坑服務區</span>
        </a>
      </div>
      <div class="col-12 d-flex justify-content-center font mt">
        <a href="https://www.google.com.tw/maps/place/%E6%9D%B1%E5%B1%B1%E6%9C%8D%E5%8B%99%E5%8D%80/@23.286527,120.3959486,17z/data=!3m2!4b1!5s0x346e8ed236a864cb:0xf4da966f0bf7c4e5!4m6!3m5!1s0x346e0448d309050f:0x60730b3b3aae9d49!8m2!3d23.2865221!4d120.3985235!16s%2Fg%2F155r26yf?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDMwMi4wIKXMDSoASAFQAw%3D%3D">
          <span>東山服務區</span>
        </a>
      </div>
      <div class="col-12 d-flex justify-content-center font mt">
        <a href="https://www.google.com.tw/maps/place/%E9%97%9C%E5%BB%9F%E6%9C%8D%E5%8B%99%E5%8D%80+(%E5%8D%97%E5%90%91)/@22.9315004,120.3484191,17z/data=!3m1!4b1!4m6!3m5!1s0x346e6d9359db80f3:0xc9950b5923eab1e1!8m2!3d22.9314955!4d120.350994!16s%2Fg%2F11s7r3s56d?hl=zh-TW&entry=ttu&g_ep=EgoyMDI1MDMwMi4wIKXMDSoASAFQAw%3D%3D">
          <span>關廟服務區</span>
        </a>
      </div>
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
