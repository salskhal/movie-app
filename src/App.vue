<template>
  <nav>
    <router-link to="/" class="logo">SalsMovie</router-link>
    <div class="movie-search">
      <input type="text" />
      <button>Search</button>
    </div>
  </nav>
  <router-view />
</template>

<style>

@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap');

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
  min-height: 100vh;
  background: orange;
  font-family: "Inter", sans-serif;
}

nav{
  display: flex;
  padding: 10px 20px;
  justify-content: space-between;
}

.logo{
  text-decoration: none;
  color: white;
  font-weight: bold;
  text-transform: uppercase;
  font-size: 2rem;
  transition: all .25s ease-in-out;
}

.logo:hover{
  color: rgb(230, 221, 221);
}


/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
} */

/* nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
} */
</style>
