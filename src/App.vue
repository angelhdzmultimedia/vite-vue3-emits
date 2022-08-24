<script>
import { defineComponent } from 'vue';
import Counter from './components/Counter.vue';

export default defineComponent({
  components: {
    Counter,
  },

  setup() {
    function onCountChange(count) {
      alert(`[COUNT]: ${count}`);
    }

    return {
      onCountChange,
    };
  },
});
</script>

<template>
  <Counter @change="onCountChange" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
