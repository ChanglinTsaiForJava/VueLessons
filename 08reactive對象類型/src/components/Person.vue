<!-- vue 內部的標籤 template/script(js/ts)/ style -->
<template>
  <!-- html 結構-->
  <div class="Person">
    <h3>a {{ car.brand }} costs {{ car.price }}</h3>
    <button @click="addPrice">add 10 dollars</button>
    <button @click="changeFirstName">chage name of the game</button>
    <button @click="changeTag">chage monk tag</button>
    <h3>test {{ monk.a.b.c }}</h3>
    <br />
    <h2>gameList:</h2>
    <ul>
      <li v-for="game in games" v-bind:key="game.id">
        {{ game.name }}
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup name="Person">
//reactive 適合這樣（多層資料）
import { reactive } from 'vue'
// 響應式>>import ref
// data
let car = reactive({ brand: 'benz', price: 100 })
let games = reactive([
  { id: '1', name: 'tlou1' },
  { id: '2', name: 'atom' },
])
let monk = reactive({
  a: {
    b: {
      c: '666',
    },
  },
})
//methods
function addPrice() {
  if (car.price < 400) {
    car.price += 10
  } else {
    car.price += 1
  }
}
function changeFirstName() {
  games[0].name = 'tlou2'
}

function changeTag() {
  monk.a.b.c = '999'
}
</script>

<style scoped>
/* 外衣 */
</style>
