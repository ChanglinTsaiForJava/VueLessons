<!-- vue 內部的標籤 template/script(js/ts)/ style -->
<template>
  <!-- html 結構-->
  <div class="person">
    <h1>hello!</h1>
    <h3>name = {{ name }}</h3>
    <h3>age = {{ age }}</h3>
    <button @click="changeName">changeName</button>
    <button @click="changeAge">changeAge</button>
  </div>
</template>

<script lang="ts">
//這是 ES6（JavaScript 的一個標準）語法，意思是「導出這個物件作為這個模組的預設輸出」。
//換句話說，當別人 import 這個檔案時，拿到的就是這個 { name: 'App' } 的物件（或整個 Vue 元件）。
export default {
  name: 'Person', //組件名字

  setup() {
    //數據
    //注意 此時的變數不是響應式 所以上面的按鈕雖然讓他改了 但不畫面不會顯示
    let name = '張三'
    let age = 18
    let tel = '123456'
    //只需要return母版需要的
    //方法
    function changeName() {
      name = 'jack'
    }
    function changeAge() {
      age = 20
    }
    function changeTel() {
      tel = '987655'
    }
    return { name, age, changeAge, changeName }
  },
}

//Js/TS交互
</script>

<style>
/* 外衣 */
.person {
  background-color: blue;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}
</style>
