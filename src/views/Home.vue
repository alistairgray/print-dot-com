<template>
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
      <router-view/>
    </header>
    <main>
      <h1>Frequent Flyers</h1>
      <div id="launch">
       <h3>Launch your flyers today ... </h3>
      </div>
    </main>
</template>