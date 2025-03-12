<script>
export default {
  emits: ['action'],
  props: {
    color: {
      type: String,
      default: '',
      validator: (value) => {
        return ['', 'primary', 'dis'].includes(value)
      },
    },
  },
  data() {
    return {}
  },
}
</script>
<template>
  <button class="btn" :class="color" @click="$emit('action')"><slot /></button>
</template>
<style scoped>
.primary {
  background-color: rgb(18, 180, 18);
  color: white;
  border: none;
}
button {
  padding: 7px;
  background-color: transparent;
  border: 2px solid rgb(29, 236, 29);
  color: rgb(255, 255, 255);
  font-weight: 500;
  font-size: 15px;
  border-radius: 7px;
  margin-bottom: 5px;
  margin-left: 10px;
}
.dis {
  background-color: brown;
  color: white;
  border: none;
}
</style>
