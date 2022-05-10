<template>
  <h1 @click="increase">
  {{ count }} / {{ doubleCount }}
  </h1>
  <h1>
  {{ message }} / {{ reversedMessage }}
  </h1>
</template>

<script>
import { ref, computed, watch, onMounted } from 'vue'

export default {
  setup() {
    const count = ref(0)
    const doubleCount = computed(() => count.value * 2)
    function increase() {
      count.value += 1
    }

    const message = ref('Hello World!')
    const reversedMessage = computed(() => {
      return message.value.split('').reverse().join('')
    })

    watch(message, newValue => {
      console.log(newValue)
    })
    function changeMessage() {
      message.value = 'Good?!'
    }

    // created 라이프 사이클
    console.log(message.value)

    onMounted(() => {
      console.log(count.value)
    })

    return {
      count,
      doubleCount,
      increase,
      message,
      changeMessage,
      reversedMessage
    }

  }
}
</script>

