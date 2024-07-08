<template>
  <div class="mainPage">
    <TypingTest/>
  </div>
</template>
<script lang="ts">
import TypingTest from '../components/typing-test/typing-test.vue';

export default {
  components: {
    TypingTest,
  }
}
</script>
<style>
.mainPage {
  position: absolute;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  height: 100vh;
  width: 100vw;
}
</style>