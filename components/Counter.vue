<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps({
  count: {
    default: 0,
  },
})

const counter = ref(props.count)
</script>

<template>
  <div class="flex w-min border border-gray-400/50 rounded-md">
    <button
      class="border-r border-gray-400/50 p-2 font-mono outline-none hover:bg-gray-400/20"
      @click="counter -= 1"
    >
      -
    </button>
    <span class="m-auto p-2">{{ counter }}</span>
    <button
      class="border-l border-gray-400/50 p-2 font-mono outline-none hover:bg-gray-400/20"
      @click="counter += 1"
    >
      +
    </button>
  </div>
</template>
