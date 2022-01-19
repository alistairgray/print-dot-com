<template>
  <div id="app">
    <header>
      <nav>
        <router-link to="/">
          <span>Home</span>
        </router-link>
        <router-link to="/products">
          <span>Products</span>
        </router-link>
      </nav>
      <div>
        <span>Cart</span>
      </div>
      <router-view />
    </header>
  </div>
</template>

<script>
  import flyers from './json/flyers.json'
  export default {
    name: 'App',
    data() {
      return {
        inventory: flyers
      }
    },
    components: {
      
    }
  }

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
