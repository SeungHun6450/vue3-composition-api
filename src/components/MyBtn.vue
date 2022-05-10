<template>
  <div  
    v-bind="$attrs"
    class="btn"
    @click="hello">
    <slot></slot>  
  </div>
</template>

<script>
import { onMounted } from 'vue'

export default {
  inheritAttrs: false,
  props: {
    color: {
      type: String,
      default: 'gray'
    }
  },
  emits: ['hello'],
  // mounted() {
  //   console.log(this.color)
  //   console.log(this.$attrs)
  // },
  // methods: {
  //   hello() {
  //     this.$emit('hello')
  //   }
  // },
  // 기존에 this를 통해 바로 활용할 수 있지만,
  // setup에서는 mounted를 props와 context를 이용해야한다.

  setup(props, context) {
    function hello() {
      context.emit('hello')
    }
    onMounted(() => {
      console.log(props.color)
      console.log(context.attrs)
    }) 

    return {
      hello
    }
  }
}

</script>