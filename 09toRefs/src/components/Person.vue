<!-- vue 內部的標籤 template/script(js/ts)/ style -->
<template>
  <!-- html 結構-->
  <div class="Person">
    <h2>{{ age }}</h2>
    <h2>{{ name }}</h2>
    <button @click="changeAge">change age += 22</button>
    <button @click="changeName">change name to dingdong</button>
  </div>
</template>

<script lang="ts" setup name="Person">
import { reactive, toRefs } from 'vue'
//data
let person = reactive({
  name: 'jack',
  age: 18,
})

//解構賦值 若使用直接解構 出來的不會是響應式 要用toRefs
// let { name, age } = person
let { name, age } = toRefs(person)
//method
function changeName() {
  name.value = 'dingdong'
  console.log(name.value)
  console.log(person.name)
}
function changeAge() {
  age.value += 2
  console.log(age.value)
  console.log(person.age)
}
</script>

<style scoped>
/* 外衣 */
</style>
