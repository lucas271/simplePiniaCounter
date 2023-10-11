
<template>
  <div class="about">
    <div class="count">
      <div v-if="countInput === true" style="display: flex;">
        <input type="number" v-model="count">
        <button @click="countInput = false">X</button>
      </div>
      <div v-else @click="countInput = true">{{ count }}</div>
    </div>
    <div class="buttons">
      <button @click="increment">+</button>
      <button @click="decrement">-</button>
    </div>
    <hr>
    <div>
      This count is: {{ oddOrEven }}
    </div>
  </div>
</template>

<script setup lang="ts">
import {useCounterStore} from '@/stores/counter'
import { storeToRefs } from 'pinia';
import { ref } from 'vue';

const countInput = ref<boolean>(false)
const {count, oddOrEven} = storeToRefs(useCounterStore())
const {increment, decrement} = useCounterStore()


</script>

<style>
  .count{
    font-size: 60px;
    margin: 20px;
  }
  .buttons button{
    font-size: 40px;
    margin: 10px;
  }
</style>