<script setup>
import { ref } from 'vue';

const activeButton = ref('one');

const clickOne = () => {
  activeButton.value = 'one';
};

const clickThree = () => {
  activeButton.value = 'three';
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

  <div v-if="activeButton === 'one'" class="container-fluid  page1 mt-2 ">
    <div class="row">
      <div class="col-6 d-flex justify-content-center">
        <div class="row">
          <div class="col-12 d-flex justify-content-center font">
            中壢服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            湖口服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            泰安服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            西螺服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            新營服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            仁德服務區
          </div>
        </div>
      </div>
      <div class="col-6 d-flex justify-content-center">
        <div class="row">
          <div class="col-12 d-flex justify-content-center font">
            中壢服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            湖口服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            泰安服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            西螺服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            新營服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            仁德服務區
          </div>
        </div>
      </div>
    </div>
  </div>

  <div v-if="activeButton === 'three'" class="container-fluid page2 mt-2">
    <div class="row">
      <div class="col-6 d-flex justify-content-center ">
        <div class="row">
          <div class="col-12 d-flex justify-content-center font">
            木柵休息站
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            關西服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            西湖服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            清水服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            南投服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            古坑服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            東山服務區
          </div>
          <div class="col-12 d-flex justify-content-center  font mt-5">
            新化休息站
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            關廟服務區
          </div>
        </div>
      </div>
      <div class="col-6 d-flex justify-content-center">
        <div class="row">
          <div class="col-12 d-flex justify-content-center font">
            關西服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            寶山休息站
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            西湖服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            清水服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            南投服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            古坑服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            東山服務區
          </div>
          <div class="col-12 d-flex justify-content-center font mt-5">
            新化休息站
          </div>
          <div class="col-12 d-flex justify-content-center  font mt-5">
            關廟服務區
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
body {
  overflow: hidden;
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
.page1,.page2{
  overflow-y: hidden;
}
.container-fluid {
  overflow: auto; /* Enable scrolling for content containers */
}
.font{
  font-size: 14px;
}
</style>
