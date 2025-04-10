<!-- vue 內部的標籤 template/script(js/ts)/ style -->

<template>
  <!-- html 結構-->
  <div class="Person">
    <h1>監視ref定義的基本類別數據</h1>
    <h2>{{ sum }}</h2>
    <button @click="changeSum">changeSum</button>
  </div>
</template>

<script lang="ts" setup name="Person">
import { ref, watch } from 'vue'
//data
let sum = ref(0)
//method
function changeSum() {
  sum.value += 10
}

//watch watch(who?, return function) 一但who的值改變 就會觸發下面的函數
//watch(
//   source,   // a ← 要監聽的東西
//   callback, // b ← (更新,舊版){邏輯}
//   options   // c ← 選項（可選）
// )

//帶有停止監聽邏輯
//如果watch有賦值 代表他有停止監聽的函數以及功能
// 如果沒有的話他就是像一個java的void方法
const stopwatch = watch(sum, (newValue, oldValue) => {
  console.log('sum is changing value', newValue, oldValue)
  if (newValue >= 100) {
    stopwatch()
  }
})
//沒有停止監聽的邏輯
//watch(sum, (newValue, oldValue) => {
//   console.log('sum is changing value', newValue, oldValue);
// });
</script>

<style scoped>
/* 外衣 */
</style>
