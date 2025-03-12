<script>
import AppButton from './components/AppButton.vue'
import AppComponentOne from './components/AppComponentOne.vue'
import AppComponentTwo from './components/AppComponentTwo.vue'
import AsyncComponent from './components/AsyncComponent.vue'
import Header from './components/Header.vue'

export default {
  components: {
    Header,
    AppButton,
    AppComponentOne,
    AppComponentTwo,
    AsyncComponent,
  },
  data() {
    return {
      isState: 'One',
    }
  },
  computed: {
    componentName() {
      return 'AppComponent' + this.isState
    },
    oneColor() {
      return this.isState === 'One' ? 'primary' : ''
    },
    twoColor() {
      return this.isState === 'Two' ? 'primary' : ''
    },
  },
}
</script>

<template>
  <Header></Header>
  <div class="container">
    <AsyncComponent></AsyncComponent>
    <h1>Динамические компоненты</h1>
    <AppButton @action="isState = 'One'" :color="oneColor">One</AppButton>
    <AppButton @action="isState = 'Two'" :color="twoColor">Two</AppButton>
    <hr />
    <keep-alive>
      <component :is="componentName"></component>
    </keep-alive>
  </div>
</template>

<style scoped>
.container {
  background-color: rgb(54, 51, 51);
  color: rgb(230, 229, 229);
  border-radius: 10px;
  width: 97%;
  height: auto;
  padding: 5px;
  margin-top: 10px;
}
</style>
