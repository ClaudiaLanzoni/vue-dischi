<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main,
    
  }
}
</script>

<style lang="scss">

@import "./style/variables.scss";
@import "./style/general.scss";

#app {
  font-style: $bodyFont;
}
</style>
