<template>
  <div>
    <h3>ADD TODO</h3>
    <form @submit.prevent="handleSubmit">
      <input type="text" :value="todoTxt" @input="handleInput" />
      <button type="submit">확인</button>
    </form>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  props: {
    todoTxt: {
      type: String,
      required: true,
    },
  },
  methods: {
    handleInput(event: InputEvent) {
      const eventTarget = event.target as HTMLInputElement;
      const { value } = eventTarget;

      this.$emit('input', value);
    },
    handleSubmit() {
      this.$emit('add');
    },
  },
});
</script>

<style scoped></style>
