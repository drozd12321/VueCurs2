<script>
export default {
  data() {
    return {
      dt: new Date(),
    }
  },
  mounted() {
    setInterval(() => {
      this.dt = new Date()
    }, 1000)
  },
}
</script>
<template>
  <div class="head">
    <h3>Новости на {{ dt }}</h3>
  </div>
</template>
<style scoped>
header {
  margin: 0;
}
.head {
  background-color: rgb(61, 61, 65);
  height: 50px;
  width: 99%;
  margin-top: 0;
  padding: 10px;
  color: white;
  padding: 15px;
}
h3 {
  margin: 0;
}
</style>
