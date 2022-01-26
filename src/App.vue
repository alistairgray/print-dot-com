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
      <div id="cart">
        <span>Cart</span>
      </div>
      
    </header>
    <main>
      <h1>Frequent Flyers</h1>
      <div id="launch">
        <router-link to="/products">
          <h3>Launch your flyers today ... </h3>
       </router-link>
      </div>
    </main>
    <router-view/>
  </div>
</template>

<script>
  import flyers from './json/flyers.json'
  import global from './global'
  export default {
    name: 'App',
    setup() {
      const {state} = global;
      return {state}
    },
    data() {
      return {
        inventory: flyers,
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
  color: #fff;
  background: url('./assets/color-background-ff.jpg');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
main {
  text-align: center;
}
main h1 {
  font-size: 115pt;
}
nav {
  max-height: 200px;
}
a {
  margin-left: 15px;
  text-decoration: none;
  color: #fff;
}
a:hover {
  text-decoration: underline;
}
#cart {
  float: right;
  margin-right: 15px;
  position: relative;
}
#launch {
  border: 7px dashed #AE8799;
  max-width: 150px;
  margin: 0 auto;
}

</style>
