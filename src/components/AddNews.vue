<script>
export default {
  props: {
    title: String,
    description: String,
    id: Number,
    isOpen: Boolean,
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
      if (this.localOpen) {
        this.$emit('openNews')
      } else {
        this.$emit('closeNews')
      }
    },
  },
}
</script>
<template>
  <div class="cont">
    <div class="news">
      <h3>{{ title }}</h3>
      <button @click="open">{{ localOpen ? 'Закрыть' : 'Открыть' }}</button>
      <div class="new" v-if="localOpen">
        <hr />
        <p>{{ description }}</p>
        <button @click="writeNews" class="btn primary">Прочесть новость</button>
      </div>
    </div>
  </div>
</template>
<style>
.primary {
  background-color: rgb(3, 77, 3);
  color: white;
  border: none;
}
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
