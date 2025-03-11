<script>
export default {
  props: {
    openNews: Number,
  },
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
    <span>Открыто: {{ openNews }}</span>
  </div>
  <div></div>
</template>
<style scoped>
header {
  margin: 0;
}
span {
  color: white;
  font-size: 20px;
}
.head {
  background-color: rgb(61, 61, 65);
  height: auto;
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
