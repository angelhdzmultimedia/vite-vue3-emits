<script>
import { defineComponent } from 'vue';
import Counter from './components/Counter.vue';

export default defineComponent({
  components: {
    Counter,
  },

  setup() {
    function onCountChange(count) {
      alert(`[Event]: change = ${count}`);
    }

    return {
      onCountChange,
    };
  },
});
</script>

<template>
  <div class="column items-center">
    <h1 class="color-primary">Counter</h1>
    <Counter @change="onCountChange" />
  </div>
</template>

<style scoped></style>
