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
      <div class="col-12 d-flex justify-content-center font mt-2">關西服務區</div>
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
  font-size:48px;
}
.font2{
  font-size:24px;
}
.mt { 
  margin-top: 30px !important;
}
</style>
