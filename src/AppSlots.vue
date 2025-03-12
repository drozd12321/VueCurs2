<script>
import Header from './components/Header.vue'
import AppBlock from './components/AppBlock.vue'
import AppList from './components/AppList.vue'

export default {
  components: {
    Header,
    AppBlock,
    AppList,
  },
  data() {
    return {}
  },
}
</script>

<template>
  <Header></Header>
  <AppList>
    <template #default="{ iter, idx }">
      <span style="color: 'red'">
        <strong> {{ idx + 1 }}</strong>
        <span> Item: {{ iter }}</span>
      </span>
    </template>
  </AppList>
  <AppBlock>
    <template #cont>
      <p>Важный текст</p>
    </template>
    <template #head> Шапка </template>
    <template #footer>Это footer</template>
  </AppBlock>
</template>

<style scoped></style>
