<template>
  <hr />
  <h4>{{ title }}</h4>
  <ul>
    <li v-for="item in news">{{ item.title }}<span v-if="item.isRead">!!!</span></li>
  </ul>
</template>
<script>
export default {
  data() {
    return {}
  },
  inject: ['title', 'news'],
}
</script>
<style></style>
