<!-- 메소드 이벤트 핸들러 -->

<!-- 1번 예시 -->
<!-- <template> -->
<!-- 인수를 넣어주지 않으면 event객체가, 인수를 넣으면 인수가 매개변수로 받아진다.
     인수 뒤쪽에 ','를 적어주고 $event객체를 직접적으로 명시가 가능하다. -->
  <!-- <button @click="handler">
    Click 1
  </button>
  <button @click="handler('hi', $event)">
    Click 2
  </button>
</template>

<script>
export default {
  methods: {
    handler(msg, e) {
      // 인수를 넣어주지 않으면 event객체가, 인수를 넣으면 인수가 매개변수로 받아진다.
      console.log(msg)
      console.log(e)
    }
  }
}
</script> -->

<!-- 2번예시 -->
<!-- ','를 통해 여러개의 함수나 메소드를 동시에 실행할 수 있다. 이때 ()는 꼭 써줘야 정상적으로 동작한다.  -->
<!-- <template>
  <button @click="handlerA(), handlerB()">
    Click me!
  </button>
</template>

<script>
export default {
  methods: {
    handlerA() {
     console.log('A')
    },
    handlerB() {
     console.log('B')
    }
  }
}
</script> -->

<!-- 이벤트 수식어 once:단 한번만 실행, prevent: 기본 동작 방지 -->
<!-- <template>
  <a
    href="https://naver.com"
    target="_blank"
    @click.once.prevent="handler">
    NAVER
  </a>
</template>

<script>
export default {
  methods: {
    handler(e) {
      console.log('ABC!')
    }
  }
}
</script> -->

<!-- 이벤트 수식어 stop: 이벤트 버블링을 방지하기 위해 사용, capture: 이벤트 캡쳐링을 방지하기 위해 사용 -->
<!-- <template>
  <div
    class="parent"
    @click="handlerA"
    > -->
  <!-- <div
    class="parent"
    @click.capture="handlerA"
    > -->
    <!-- <div
      class="child"
      @click.stop="handlerB"></div> -->
    <!-- <div
      class="child"
      @click="handlerB"></div> -->
  <!-- </div>
</template> -->

<!-- <script>
export default {
  methods: {
    handlerA() {
      console.log('A')
    },
    handlerB() {
      console.log('B')
    }
  }
}
</script>
<style scoped lang="scss">
.parent {
  width: 200px;
  height: 100px;
  background-color: royalblue;
  margin: 10px;
  padding: 10px;
  .child {
    width: 100px;
    height: 100px;
    background-color: orange;
  }
}
</style> -->

<!-- 이벤트 수식어 self: 정확한 영역(노출된 부분을)을 선택해야 이벤트가 발생-->
<!-- passive: 로직과 화면에 변화를 독립 시켜 부하를 줄여준다. -->
<!-- <template> -->
  <!-- <div
    class="parent"
    @click.self="handlerA"
    > -->
  <!-- <div
    class="parent"
    @wheel.passive="handler"
    >
    <div
      class="child"></div>
  </div>
</template> -->

<!-- <script>
export default {
  methods: {
    handler(e) {
      for(let i = 0 ; i < 10000 ; i += 1)
      console.log(e)
    },
    handlerA() {
      console.log('A')
    },
    handlerB() {
      console.log('B')
    }
  }
}
</script>
<style scoped lang="scss">
.parent {
  width: 200px;
  height: 100px;
  background-color: royalblue;
  margin: 10px;
  padding: 10px;
  overflow: auto;
  .child {
    width: 100px;
    height: 2000px;
    background-color: orange;
  }
}
</style> -->

<!-- key 수식어 -->
<template>
  <input 
    type="text"
    @keydown.ctrl.shift.a="handler" />
    <!-- @keydown.enter="handler" /> -->
</template>

<script>
export default {
  methods: {
    handler() {
      console.log('Enter!')
    }
  }
}
</script>