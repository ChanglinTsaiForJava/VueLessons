<!-- vue 內部的標籤 template/script(js/ts)/ style -->
<template>
  <!-- html 結構-->
  <div class="Person">
    <h2>{{ a }}</h2>
    <h1>hello!</h1>
    <h3>name = {{ name }}</h3>
    <h3>age = {{ age }}</h3>
    <h3>{{ a }}</h3>
    <button @click="changeName">changeName</button>
    <button @click="changeAge">changeAge</button>
  </div>
</template>
<!-- 第一個script是專門配置組件名字 -->
<!-- <script lang="ts">
//這是 ES6（JavaScript 的一個標準）語法，意思是「導出這個物件作為這個模組的預設輸出」。
//換句話說，當別人 import 這個檔案時，拿到的就是這個 { name: 'App' } 的物件（或整個 Vue 元件）。
export default {
  name: 'Person',
}
//Js/TS交互
</script> -->

<!-- 第二個script是專門配置api 除非安裝插件“npm i vite-plugin-vue-setup-extend -D/ 再去vite config import-->
<!-- 語法糖 setup中的會自動return -->
<script lang="ts" setup name="Person123">
let a = 666
//數據
//注意 此時的變數不是響應式 所以上面的按鈕雖然讓他改了 但不畫面不會顯示
let name = '張三'
let age = 18
let tel = '123456'
//只需要return母版需要的
//方法
function changeName() {
  name = '123'
}
function changeAge() {
  age = 12
}
function changeTel() {
  tel = '123123123213'
}
</script>

<style scoped>
/* 外衣 */
</style>
