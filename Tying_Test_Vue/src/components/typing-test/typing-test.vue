<template>
  <div class="bg-grey-darken-3 rounded-xl typingTestBody">
    <div class="typingArea">
      <span v-for="char in test.length" :key="char">
        {{ test[char-1] }}
      </span>
    </div>
  </div>
</template>
<script lang="ts">
import wordsJson from './words.json';

export default {
  beforeMount() {
    this.setUpTest();
  },
  methods: {
    setUpTest() {
      const words = wordsJson.commonWords;
      this.charactersTyped = 0;
      this.test = words[Math.floor(Math.random() * words.length)] + " ";
      for(let i = 0; i < 1000; i++) {
        this.test = this.test.concat(words[Math.floor(Math.random() * words.length)]);
        this.test = this.test.concat(" ");
      }
      console.log(this.test);
    }
  },
  data() {
    return {
      charactersTyped: 0,
      test: "",
    }
  }
}
</script>
<style>
.typingArea {
  width: 95%;
  height: 95%
}

.typingTestBody {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 60vh;
  width: 80vw;
  overflow: hidden;
}
</style>