<template>
  <div class="about">
    <h1>About</h1>

    <button class="counter-button">
      {{ count }}
    </button>
  </div>
</template>

<script setup lang="ts">
  import { useCounterStore } from '@/stores/counter';
import { storeToRefs } from 'pinia';

  const {count} = storeToRefs(useCounterStore())
</script>