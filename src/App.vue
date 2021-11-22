<template>
  <div id="app">
    <img id="logo-banner" src="../images/banner.png" alt="logo" /> <br />
    <div id="nav">
      
    </div>
    <router-view/>
  </div>
</template>

<style>
img {
  width: 100vw;
  border-bottom: double #280c60 20px;

}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #e8e8ef;
  height: 100vh;
  
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
