<template>
  <Home />
</template>

<script>
import Home from './routes/Home';

export default {
  name: 'App',
  components: {
    Home
  }
}
</script>

<style lang="scss" src="./scss/index.scss"></style>
<style lang="scss">
#app {
  font-family: Proxima Nova;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
