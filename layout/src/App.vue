<template>
  <div id="app">
    <Header />
    <div class="app__wrapper">
      <Sidebar />
      <Main />
    </div>
  </div>
</template>

<script>
import Header from './components/header/Header.vue'
import Sidebar from './components/sidebar/Sidebar.vue'
import Main from './components/main/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Sidebar,
    Main
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  transition: 0.3s;

}

#app {
  font-family: 'PT Sans';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.app__wrapper {
  display: flex;
  gap: 36px;
  margin-top: 24px;
  width: calc(100% - 200px);
  margin: $mid-gap 100px 36px;
}

@media(max-width: 1300px) {
  .app__wrapper {
    width: calc(100% - 32px);
    margin: 24px 16px 36px;
  }
}

@media(max-width: 800px) {
  .app__wrapper {
    margin: 12px 16px 36px;
  }
}
</style>
