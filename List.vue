<template>
  <div v-for="(item, i) in state.list" :ref="el => { divs[i] = el }">
    {{ item }}
  </div>
  <button @click="resetList">重置列表</button>
</template>

<script>
  import { ref, reactive, onBeforeUpdate } from 'vue'

  export default {
    setup() {
      let state = reactive({
        list:['html', 'css', 'javascript']
        })
      const divs = ref([])

      // make sure to reset the refs before each update
      onBeforeUpdate(() => {
        console.log(divs.value)
      })

      function resetList() {
        state.list = ['高质量', '高性能', '精通css', 'css世界']
      }

      return {
        state,
        divs,
        resetList
      }
    }
  }
</script>