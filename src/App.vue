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
      news: [
        { title: 'News 1', description: 'Description 1', id: 1, isOpen: false, isRead: false },
        { title: 'News 2', description: 'Description 1', id: 2, isOpen: false, isRead: false },
        { title: 'News 3', description: 'Description 1', id: 3, isOpen: false, isRead: false },
        { title: 'News 4', description: 'Description 1', id: 4, isOpen: false, isRead: false },
        { title: 'News 5', description: 'Description 1', id: 5, isOpen: false, isRead: false },
      ],
      openNews: 0,
      writeNews: 0,
    }
  },
  methods: {
    readNews(i) {
      console.log(i)
      this.writeNews++
      this.news.map((item) => (item.id === i ? (item.isRead = !item.isRead) : ''))
    },
    unreadNews(i) {
      console.log(i)
      this.writeNews--
      this.news.map((item) => (item.id === i ? (item.isRead = !item.isRead) : ''))
    },
  },
}
</script>

<template>
  <Header :writeNews="writeNews" :openNews="openNews"></Header>

  <main>
    <AddNews
      v-for="item in news"
      :title="item.title"
      :description="item.description"
      :key="item.id"
      :is-open="item.isOpen"
      :id="item.id"
      :is-read="item.isRead"
      @openNews="this.openNews++"
      @closeNews="this.openNews--"
      @writeNews="readNews"
      @unwriteNews="unreadNews"
    ></AddNews
    >npm
  </main>
</template>

<style scoped></style>
