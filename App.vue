<template>
  <h1>Hello Vite + Vue 3!</h1>
  <p>Edit ./App.vue to test hot module replacement (HMR).</p>
  <p>
    <span>Count is: {{ count }}</span>
    <button @click="add">increment</button>
  </p>
  <Button></Button>
  <List />
</template>

<script>
import Button from './Button.vue'
import List from './List.vue'
export default {
  data: () => ({ count: 0 }),
  components: {
    Button,
    List
  },
  methods: {
    add() {
      this.count += 1
    }
  },
}
</script>

<style scoped>
h1 {
  color: #4fc08d;
}

h1, p {
  font-family: Arial, Helvetica, sans-serif;
}
</style>
