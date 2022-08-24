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
  <div class="row items-center gap-md">
    <button
      class="cursor-pointer borderless rounded pa-md bg-primary color-white"
      @click="decrease"
    >
      -
    </button>
    <h3 class="color-primary">{{ count }}</h3>
    <button
      class="cursor-pointer borderless rounded pa-md bg-primary color-white"
      @click="increase"
    >
      +
    </button>
  </div>
</template>
