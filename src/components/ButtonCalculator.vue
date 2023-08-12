<template>
  <button @click="handleClick">{{ label }}</button>
</template>

<script>
export default {
  props: ['label'],
  // methods: {
  //   handleClick() {
  //     this.$emit('click', this.label);
  //   }
  // }
};
</script>

<style scoped>
button {
  font-size: 18px;
  padding: 10px;
}
</style>
