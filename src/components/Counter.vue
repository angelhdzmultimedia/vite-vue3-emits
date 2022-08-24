<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  emit: ['change'],
  setup(props, { emit }) {
    const count = ref(0);

    function increase() {
      count.value++;
      emit('change', count.value);
    }

    function decrease() {
      count.value--;
      emit('change', count.value);
    }

    return {
      increase,
      decrease,
      count,
    };
  },
});
</script>

<template>
  <div>
    <h1>Counter</h1>
    <button @click="decrease">-</button>
    <span>{{ count }}</span>
    <button @click="increase">+</button>
  </div>
</template>
