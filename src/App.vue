<!-- 개요 -->
<!-- <template>
  <h1 @click="increase">
  {{ count }} / {{ doubleCount }}
  </h1>
  <h1>
  {{ message }} / {{ reversedMessage }}
  </h1>
</template>

<script>
export default {
  data() {
    return {
      message: 'Hello world!!',
      count: 0
    }
  },
  computed: {
    doubleCount() {
      return this.count * 2
    },
    reversedMessage() {
      return this.message.split('').reverse().join('')
    }
  },
  watch: {
    message(newValue) {
      console.log(newValue)
    }
  },
  created() {
    console.log(this.message)
  },
  mounted() {
    console.log(this.message)
  },
  methods: {
    increase() {
      this.count += 1
    }
  }
}
</script> -->

<!-- 반응형 데이터(반응성) -->
<!-- <template>
  <div @click="increase">
    {{ count }}
  </div>
</template>

<script>
// 반응성을 위해 ref를 가져와서 사용
import { ref } from 'vue'

  export default {
    // Composition Api 사용 전
    // data() {
    //   return {
    //     count: 0
    //   }
    // },
    // methods: {
    //   increase() {
    //     this.count += 1
    //   }
    // }
    
    // Composition Api 사용 후
    setup() {
      // 반응성 x
      // let count = 0;
      // function increase() {
      //   count += 1
      // }

      // ref추가 후 반응성 O
      let count = ref(0);
      function increase() {
        // 데이터 처럼 사용해야 한다.
        count.value += 1
      }

      return {
        count,
        increase
      }
    }
  }
</script> -->


<!-- props, context -->
<template>
  <MyBtn
    class="Hun"
    style="color: red;"
    color="#ff0000"
    @hello="log">
    Apple  
  </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default {
  components: {
    MyBtn
  },
  methods: {
    log() {
      console.log('Hello world!')
    }
  }
}
</script>