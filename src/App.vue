<template>
  <nav>
    <router-link to="/" class="logo">SalsMovies</router-link>
  </nav>
  <router-view />
  <footer>👨🏿‍💻 with ❤️ by <a href="https://github.com/salskhal" target="blank">@salskhal</a></footer>
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
  background: #06476B;
  font-family: "Inter", sans-serif;
}

nav{
  display: flex;
  padding: 10px 20px;
  justify-content: space-between;
}

.logo{
  text-decoration: none;
  color: #022f47;
  font-weight: bold;
  text-transform: uppercase;
  font-size: 1.3rem;
  transition: all .25s ease-in-out;
}
footer{
  font-size: 20px;
  color: white;
  padding: 10px;
  text-align: center;
  margin-top: auto;
}

footer a{
  color: white;
  text-decoration: underline;
}
</style>
