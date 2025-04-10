<!-- vue 內部的標籤 template/script(js/ts)/ style -->
<template>
  <!-- html 結構-->
  <div class="person">
    <h1>hello!</h1>
    <h3>name = {{ name }}</h3>
    <h3>age = {{ age }}</h3>
    <button @click="showtel">check contact</button>
    <button @click="changeName">changeName</button>
    <button @click="changeAge">changeAge</button>
  </div>
</template>

<script lang="ts">
//這是 ES6（JavaScript 的一個標準）語法，意思是「導出這個物件作為這個模組的預設輸出」。
//換句話說，當別人 import 這個檔案時，拿到的就是這個 { name: 'App' } 的物件（或整個 Vue 元件）。
export default {
  name: 'Person', //組件名字
  //可以發現選項用的寫法optionsAPI 會造成data裡面變得很混亂 （可能會有很多個vue的資料 太亂了）
  //放數據用
  data() {
    return {
      name: 'steve',
      age: 18,
      tel: '123456',
    }
  },
  //放方法用
  methods: {
    changeName() {
      this.name = 'jo'
    },
    changeAge() {
      this.age = 123
    },
    showtel() {
      alert(this.tel)
    },
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
