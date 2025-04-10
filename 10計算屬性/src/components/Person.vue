<!-- vue 內部的標籤 template/script(js/ts)/ style -->
<template>
  <!-- html 結構-->
  <div class="Person">
    <!-- v-model雙向綁定 v-bind單向 -->
    FirstName: <input type="text" v-model="firstName" /> LastName:<input
      type="text"
      v-model="LastName"
    />
    fullName:
    <span>{{ fullName }}</span>
    <button @click="changeFullName">changeFullName</button>
  </div>
</template>

<script lang="ts" setup name="Person">
import { ref, computed } from 'vue'
let firstName = ref('Steve')

let LastName = ref('Tsai')
//計算後的屬性是唯獨
// let fullName = computed(() => {
//   return firstName.value.slice(0, 1).toUpperCase() + firstName.value.slice(1) + LastName.value
// })

//下面這樣定義可讀可寫 歐耶
let fullName = computed({
  get() {
    return firstName.value.slice(0, 1).toUpperCase() + firstName.value.slice(1) + LastName.value
  },
  set(val) {
    const x = val.split(' ')
    const [fn, ln] = x
    firstName.value = fn
    LastName.value = ln
    console.log(x)
  },
})
function changeFullName() {
  fullName.value = 'jack sparrow'
}
</script>

<style scoped>
/* 外衣 */
</style>
