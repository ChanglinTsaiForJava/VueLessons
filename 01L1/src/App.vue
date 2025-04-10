<!-- vue 內部的標籤 template/script(js/ts)/ style -->
<template>
  <!-- html 結構-->
  <div class="app">
    <h1>hello!</h1>
  </div>
</template>

<script lang="ts">
//這是 ES6（JavaScript 的一個標準）語法，意思是「導出這個物件作為這個模組的預設輸出」。
//換句話說，當別人 import 這個檔案時，拿到的就是這個 { name: 'App' } 的物件（或整個 Vue 元件）。
export default {
  name: 'App', //組件名字
}

//Js/TS交互
</script>

<style>
/* 外衣 */
.app {
  background-color: darkgoldenrod;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}
</style>
