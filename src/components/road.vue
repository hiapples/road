<script setup>
import { ref } from 'vue';

const activeButton = ref('one');
const activePage = ref('one'); // 用來儲存目前顯示的頁面

const clickOne = () => {
  activeButton.value = 'one';
  activePage.value = 'one'; // 顯示 page1
};

const clickThree = () => {
  activeButton.value = 'three';
  activePage.value = 'three'; // 顯示 page2
};

// 用來檢測左右滑動
let touchstartX = 0;
let touchendX = 0;

const checkSwipe = () => {
  if (touchendX < touchstartX) {
    // 向左滑，切換到 page2
    activePage.value = 'three';
    activeButton.value ='three';
  }
  if (touchendX > touchstartX) {
    // 向右滑，切換到 page1
    activePage.value = 'one';
    activeButton.value ='one';
  }
};

const touchStart = (e) => {
  touchstartX = e.changedTouches[0].screenX;
};

const touchEnd = (e) => {
  touchendX = e.changedTouches[0].screenX;
  checkSwipe();
};
</script>

<template>
  <div class="container-fluid button-back">
    <div class="row">
      <div 
        class="button col-6 d-flex justify-content-center" 
        :class="{ active: activeButton === 'one' }"
        @click="clickOne"
      >
        國道一號
      </div>
      <div 
        class="button col-6 d-flex justify-content-center" 
        :class="{ active: activeButton === 'three' }"
        @click="clickThree"
      >
        國道三號
      </div>
      <div class="col-6 d-flex justify-content-center" style="color: brown;background-color: white;">
        <span class="mt-3 mb-3">北上</span>
      </div>
      <div class="col-6 d-flex justify-content-center" style="color: #0072E3;background-color: white;">
        <span class="mt-3 mb-3">南下</span>
      </div>
    </div>
  </div>

  <!-- 左右滑動切換頁面 -->
  <div 
    v-if="activePage === 'one'" 
    class="container-fluid page1 mt-2" 
    @touchstart="touchStart" 
    @touchend="touchEnd"
  >
    <div class="row">
      <div class="col-6 d-flex justify-content-center">
        <div class="row">
          <div class="col-12 d-flex justify-content-center font">
            中壢服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            湖口服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            泰安服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            西螺服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            新營服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            仁德服務區
          </div>
        </div>
      </div>
      <div class="col-6 d-flex justify-content-center">
        <div class="row">
          <div class="col-12 d-flex justify-content-center font">
            中壢服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            湖口服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            泰安服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            西螺服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            新營服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            仁德服務區
          </div>
        </div>
      </div>
    </div>
  </div>

  <div 
    v-if="activePage === 'three'" 
    class="container-fluid page2 mt-2" 
    @touchstart="touchStart" 
    @touchend="touchEnd"
  >
    <div class="row">
      <div class="col-6 d-flex justify-content-center ">
        <div class="row">
          <div class="col-12 d-flex justify-content-center font">
            木柵休息站
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            關西服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            西湖服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            清水服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            南投服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            古坑服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            東山服務區
          </div>
          <div class="col-12 d-flex justify-content-center  font mt-4">
            新化休息站
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            關廟服務區
          </div>
        </div>
      </div>
      <div class="col-6 d-flex justify-content-center">
        <div class="row">
          <div class="col-12 d-flex justify-content-center font">
            關西服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            寶山休息站
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            西湖服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            清水服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            南投服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            古坑服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            東山服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-4">
            新化休息站
          </div>
          <div class="col-12 d-flex justify-content-center  font mt-4">
            關廟服務區
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
html, body {
  height: 100%;
  overflow: hidden; /* 禁止上下滾動 */
  margin: 0;
  touch-action: pan-x;  /* 只允許水平方向的觸摸滾動 */
}
body {
  position: fixed; /* 固定內容 */
  width: 100%;
  overflow: hidden; /* 禁止水平滾動 */
}
.button-back {
  background-color: #b0afaf;
}
.button {
  background-color: #b0afaf;
  padding: 10px;
  cursor: pointer;
}
.active {
  background-color: #4b4b4b;
  color: white;
}
.page1, .page2 {
  overflow-y: hidden;
}
.container-fluid {
  overflow: auto;
}
.font {
  font-size: 18px;
}
.mt-4 {
  margin-top: 50px !important;
}
</style>
