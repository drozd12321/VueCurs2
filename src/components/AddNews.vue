<script>
import AppButton from './AppButton.vue'
import AppNewsList from './AppNewsList.vue'

export default {
  components: {
    AppButton,
    AppNewsList,
  },
  props: {
    title: String,
    description: String,
    id: Number,
    isOpen: Boolean,
    isRead: Boolean,
  },
  emits: {
    writeNews(i) {
      if (i) {
        return true
      }
      console.warn('No id News')
      return false
    },
    openNews: null,
    closeNews: null,
    unwriteNews: null,
  },
  data() {
    return {
      localOpen: this.isOpen,
    }
  },
  methods: {
    open() {
      this.localOpen = !this.localOpen
      if (this.localOpen) {
        this.$emit('openNews')
      } else {
        this.$emit('closeNews')
      }
    },
    writeNews() {
      this.localOpen = !this.localOpen
      this.$emit('writeNews', this.id)
      this.$emit('closeNews')
    },
    unwriteNews() {
      this.localOpen = !this.localOpen
      this.$emit('unwriteNews', this.id)
      this.$emit('closeNews')
    },
  },
}
</script>
<template>
  <div class="cont">
    <div class="news">
      <h3>{{ title }}</h3>
      <AppButton @action="open">
        {{ localOpen ? 'Закрыть' : 'Открыть' }}
      </AppButton>
      <div class="new" v-if="localOpen">
        <hr />
        <p>{{ description }}</p>
        <AppButton v-if="!isRead" @action="writeNews" color="primary">
          Прочитать Новость
        </AppButton>
        <AppButton v-else-if="isRead" @action="unwriteNews" color="dis">
          Отметить непрочитанной
        </AppButton>
        <AppNewsList></AppNewsList>
      </div>
    </div>
  </div>
</template>
<style scoped>
.new {
  width: 99%;
}
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
  margin-top: 20px;
  transition: transform 0.5s ease;
}
.news:hover {
  transform: translateY(-8px);
}

h3 {
  font-size: 25px;
}
</style>
