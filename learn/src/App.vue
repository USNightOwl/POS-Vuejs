<script>
import { debounce } from 'lodash-es'

export default {
  data() {
    return {
      count: 0,
    }
  },
  methods: {
    increment: debounce(function () {
      this.count++
    }, 500)
  },
  mounted() {
    this.increment()
  }
}
</script>

<template>
  <div class="flex flex-col items-center pt-3">
    <div class="text-lg">{{ count }}</div>
    <button @click="increment" type="button" class="border border-gray-900 rounded mt-1 p-1">Increment</button>
  </div>
</template>

<style scoped>
</style>
