<template>
  <div id="f-bg-main">
    <div id="squares-group">
      <i id="squares-first"></i>
      <i id="squares-second"></i>
      <i id="squares-third"></i>
    </div>
    <div id="shape"></div>
    <div id="left">
      <svg height="896" width="967">
        <defs>
          <path id="path-2" opacity="1" fill-rule="evenodd"
            d="M896,448 C1142.6325445712241,465.5747656464056 695.2579309733121,896 448,896 C200.74206902668806,896 5.684341886080802e-14,695.2579309733121 0,448.0000000000001 C0,200.74206902668806 200.74206902668791,5.684341886080802e-14 447.99999999999994,0 C695.2579309733121,0 475,418 896,448Z">
          </path>
          <linearGradient id="linearGradient-3" x1="0.5" y1="0" x2="0.5" y2="1">
            <stop offset="0" :stop-color="config.themeColor" stop-opacity="1"></stop>
            <stop offset="1" stop-color="#ffffff" stop-opacity="1"></stop>
          </linearGradient>
        </defs>
        <g opacity="1">
          <use xlink:href="#path-2" fill="url(#linearGradient-3)" fill-opacity="1"></use>
        </g>
      </svg>
    </div>
    <div id="right">
      <svg height="1337" width="1337">
        <defs>
          <path id="path-1" opacity="1" fill-rule="evenodd"
            d="M1337,668.5 C1337,1037.455193874239 1037.455193874239,1337 668.5,1337 C523.6725684305388,1337 337,1236 370.50000000000006,1094 C434.03835568300906,824.6732385973953 6.906089672974592e-14,892.6277623047779 0,668.5000000000001 C0,299.5448061257611 299.5448061257609,1.1368683772161603e-13 668.4999999999999,0 C1037.455193874239,0 1337,299.544806125761 1337,668.5Z">
          </path>
          <linearGradient id="linearGradient-2" x1="0.79" y1="0.62" x2="0.21" y2="0.86">
            <stop offset="0" stop-color="#ffffff" stop-opacity="1"></stop>
            <stop offset="1" :stop-color="config.themeColor" stop-opacity="1"></stop>
          </linearGradient>
        </defs>
        <g opacity="1">
          <use xlink:href="#path-1" fill="url(#linearGradient-2)" fill-opacity="1"></use>
        </g>
      </svg>
    </div>
    <slot></slot>
  </div>
</template>

<script setup>
import { ref } from "vue";

const config = ref({
  themeColor: "#79bbff",

});
</script>

<style scoped>
#f-bg-main {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgb(236, 245, 255);
  position: relative;
  overflow: hidden;
}

#squares-group {
  position: absolute;
  top: 100px;
  left: 200px;
  width: 140px;
  height: 140px;
}

#squares-group>i {
  position: absolute;
  border-radius: 8px;
  box-shadow: 0 8px 20px rgb(160, 207, 255);
}

#squares-first {
  top: 12px;
  left: 30px;
  z-index: 2;
  width: 50px;
  height: 50px;
  background-color: rgba(160, 207, 255, 0.3);
  transform: translate(0px) rotate(-10deg);

}

#squares-second {
  top: 30px;
  left: 48px;
  z-index: 1;
  width: 70px;
  height: 70px;
  background-color: rgba(160, 207, 255, 0.2);
  transform: translate(0px) rotate(10deg);
}

#squares-third {
  top: 80px;
  left: 95px;
  z-index: 3;
  width: 32px;
  height: 32px;
  background-color: rgba(160, 207, 255, 0.4);
  transform: translate(0px) rotate(0deg);
}

#shape {
  position: absolute;
  border-radius: 50%;
  width: 300px;
  height: 300px;
  background: rgb(217, 236, 255);
  bottom: -150px;
  right: -150px;
}

#left {
  position: absolute;
  left: -200px;
  bottom: -400px;
}

#right {
  position: absolute;
  right: -300px;
  top: -900px;
}
</style>