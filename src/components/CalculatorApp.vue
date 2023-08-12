<template>
  <div class="calculator">
    <input v-model="display" class="display" disabled />
    <div class="buttons">
      <Button v-for="button in buttons" :key="button" :label="button" @click="handleButtonClick(button)" />
    </div>
  </div>
</template>

<script>
import Button from './ButtonCalculator.vue';

export default {
  components: {
    Button
  },
  data() {
    return {
      display: '',
      buttons: ['7', '8', '9', '/', '4', '5', '6', '*', '1', '2', '3', '-', '0', '.', '=', '+']
    };
  },
  methods: {
    handleButtonClick(button) {
      if (button === '=') {
        try {
          this.display = eval(this.display).toString();
        } catch (error) {
          this.display = 'Error';
        }
      } else {
        this.display = this.display + button;
      }
    }
  }
};
</script>

<style scoped>
.calculator {
  width: 300px;
  margin: auto;
}

.display {
  width: 100%;
  margin-bottom: 10px;
  font-size: 24px;
  padding: 5px;
  text-align: right;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 5px;
}
</style>
