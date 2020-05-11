<template>
  <h1>Button component </h1>
  <input v-model="state.count" />
  <p>Count is: {{ state.count }}, double is: {{ state.double }}</p>
  <button @click="increment">
    increment
  </button>
  <button @click="decreasement">decreasement</button>
</template>

<script>
import { reactive, computed, ref, watchEffect } from 'vue'
export default {
  setup() {
    const count = ref(0)
    const state = reactive({
      count,
      double: computed({
        get: () => state.count * 2,
        set: () => {
          state.count -= 1
        }
      })
    })
    watchEffect(() => console.log(count.value))
    function increment() {
      state.count++
    };
    function decreasement() {
      state.double -= 2
    }

    return {
      state,
      increment,
      decreasement
    }
  }
}
</script>