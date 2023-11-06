<template>
    <div id="loading-area" class="loading-page-1">
	<div class="loader">
		<div class="loading-dot"></div>
	</div>
</div>
</template>

<style scoped>
#loading-area {
  position: fixed;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
  z-index: 999999999;
  background-position: center;
  background-repeat: no-repeat;
  background-size: 80px;
  background: #fff;
  display: flex;
  justify-content: center;
  align-items: center; }
  #loading-area .loader {
    width: 100px;
    height: 100px;
    margin: auto;
    position: relative; }
    #loading-area .loader .loading-dot {
      background-color: var(--bs-orange);
      width: 15px;
      height: 15px;
      margin: auto;
      border-radius: 50%;
      position: absolute;
      left: 0;
      right: 0;
      top: 0;
      bottom: 0;
      box-shadow: 0px 40px 0px 0px var(--bs-orange), 0px -40px 0px 0px var(--bs-orange), 40px 0px 0px 0px var(--bs-orange), -40px 0px 0px 0px var(--bs-orange), 40px 40px 0px 0px var(--bs-orange), -40px -40px 0px 0px var(--bs-orange), 40px -40px 0px 0px var(--bs-orange), -40px 40px 0px 0px var(--bs-orange);
      animation: load 3s infinite linear; }

@keyframes load {
  0% {
    transform: rotate(0deg);
    box-shadow: 0px 40px 0px 0px var(--bs-orange), 0px -40px 0px 0px var(--bs-orange), 40px 0px 0px 0px var(--bs-orange), -40px 0px 0px 0px var(--bs-orange), 40px 40px 0px 0px var(--bs-orange), -40px -40px 0px 0px var(--bs-orange), 40px -40px 0px 0px var(--bs-orange), -40px 40px 0px 0px var(--bs-orange); }
  25% {
    box-shadow: 0px 40px 0px 0px var(--bs-orange), 0px -40px 0px 0px var(--bs-orange), 40px 0px 0px 0px var(--bs-orange), -40px 0px 0px 0px var(--bs-orange), -40px -40px 0px 0px var(--bs-orange), 40px 40px 0px 0px var(--bs-orange), -40px 40px 0px 0px var(--bs-orange), 40px -40px 0px 0px var(--bs-orange); }
  50% {
    box-shadow: 0px -40px 0px 0px var(--bs-orange), 0px 40px 0px 0px var(--bs-orange), -40px 0px 0px 0px var(--bs-orange), 40px 0px 0px 0px var(--bs-orange), -40px -40px 0px 0px var(--bs-orange), 40px 40px 0px 0px var(--bs-orange), -40px 40px 0px 0px var(--bs-orange), 40px -40px 0px 0px var(--bs-orange); }
  70% {
    box-shadow: 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange); }
  75% {
    width: 10px;
    height: 10px;
    box-shadow: 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange); }
  80% {
    background-color: var(--bs-orange);
    width: 40px;
    height: 40px;
    transform: rotate(360deg);
    box-shadow: 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange); }
  85% {
    background-color: var(--bs-orange);
    width: 40px;
    height: 40px;
    transform: rotate(360deg);
    box-shadow: 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange); }
  90% {
    background-color: var(--bs-orange);
    width: 10px;
    height: 10px;
    transform: rotate(360deg);
    box-shadow: 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange), 0px 0px 0px 0px var(--bs-orange); }
  95% {
    box-shadow: 0px 40px 0px 0px var(--bs-orange), 0px -40px 0px 0px var(--bs-orange), 40px 0px 0px 0px var(--bs-orange), -40px 0px 0px 0px var(--bs-orange), 40px 40px 0px 0px var(--bs-orange), -40px -40px 0px 0px var(--bs-orange), 40px -40px 0px 0px var(--bs-orange), -40px 40px 0px 0px var(--bs-orange); }
  100% {
    transform: rotate(360deg);
    box-shadow: 0px 40px 0px 0px var(--bs-orange), 0px -40px 0px 0px var(--bs-orange), 40px 0px 0px 0px var(--bs-orange), -40px 0px 0px 0px var(--bs-orange), 40px 40px 0px 0px var(--bs-orange), -40px -40px 0px 0px var(--bs-orange), 40px -40px 0px 0px var(--bs-orange), -40px 40px 0px 0px var(--bs-orange); } }

</style>
