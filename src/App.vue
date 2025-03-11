<script>
import AddNews from './components/AddNews.vue'
import Header from './components/Header.vue'

export default {
  components: {
    Header,
    AddNews,
  },
  data() {
    return {
      title: 'Project Vue',
      news: ['News 1', 'News 2', 'News 3', 'News 4', 'News 5'],
    }
  },
}
</script>

<template>
  <Header></Header>

  <main>
    <AddNews></AddNews>
  </main>
</template>

<style scoped></style>
