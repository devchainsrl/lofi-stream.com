<template>
  <Header />
  <StreamContainer />
  <Footer />
</template>

<script>

import Footer from './components/Footer.vue'
import Header from './components/Header.vue'
import StreamContainer from './components/StreamContainer.vue'

export default {
  components: { Header, Footer, StreamContainer }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
