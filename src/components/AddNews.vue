<script>
export default {
  data() {
    return {
      title: 'Новость 1',
      descr: 'Lorem vLorem Lorem LoremLoremv  Lorem v  Lorem vv',
      isOpen: false,
    }
  },
}
</script>
<template>
  <div class="cont">
    <div class="news">
      <h3>{{ title }}</h3>
      <button @click="isOpen = !isOpen">Открыть</button>
      <p v-if="isOpen">{{ descr }}</p>
    </div>
  </div>
</template>
<style>
.cont {
  display: flex;
  justify-content: center;
}
.news {
  background-color: rgb(248, 248, 248);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.4);
  width: 500px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 6px;
  margin-top: 10px;
}
button {
  padding: 7px;
  background-color: transparent;
  border: 2px solid rgb(29, 236, 29);
  color: rgb(4, 121, 4);
  font-weight: 500;
  font-size: 15px;
  border-radius: 7px;
  margin-bottom: 5px;
}
h3 {
  font-size: 25px;
}
</style>
