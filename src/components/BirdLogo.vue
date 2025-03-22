<!-- BirdLogo.vue -->
<template>
  <div class="bird-logo">
    <div class="head-top"></div>
    <div class="beak"></div>
    <div class="eye"></div>
    <div class="head-bottom"></div>
  </div>
</template>

<style scoped>
.bird-logo {
  position: relative;
  background-color: #fff;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  box-shadow: 0px 0px 6px 0px #00000040;
}

.head-top {
  position: absolute;
  background-color: rgb(0, 0, 0);
  width: 50%;
  height: 50%;
  left: 48%;
  top: 50%;
  transform: translate(-50%, -50%);
  border-radius: 59% 41% 52% 48% / 70% 31% 69% 30%;
  &:before,
  &:after {
    content: "";
    position: absolute;
  }
  &:after {
    position: absolute;
    background-color: white;
    width: 121%;
    height: 100%;
    left: 50%;
    top: 70%;
    transform: translate(-50%, -50%);
    border-radius: 57% 43% 52% 48% / 70% 25% 75% 30%   ;
  }
}

.beak {
  position: absolute;
  background-color: rgb(0, 0, 0);
  width: 13%;
  height: 7%;
  left: 73%;
  top: 41%;
  border-top-right-radius: 99% 109%;
  z-index: 1;
  transform: rotate(355deg);
}

.eye {
  position: absolute;
  background-color: rgb(0, 0, 0);
  width: 10%;
  height: 10%;
  border-radius: 50%;
  left: 56%;
  top: 44%;
  z-index: 1;
}

.head-bottom {
  position: absolute;
  background-color: black;
  width: 50%;
  height: 24%;
  left: 25%;
  top: 49%;
  border-bottom-right-radius: 100% 205%;
  &:before,
  &:after {
    content: "";
    position: absolute;
  }
  &:after {
    position: absolute;
    background-color: rgb(255 255 255);
    width: 117%;
    height: 100%;
    left: -10%;
    top: -36%;
    border-bottom-right-radius: 99% 210%;
    border-top-left-radius: 147% 145%;

  }
}
</style>
