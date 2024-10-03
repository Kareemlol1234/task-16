<template>
  <nav><router-link to="/">Home</router-link> |</nav>
  <router-view />
</template>

<style>
nav {
  text-align: center;
  margin: 30px;
  padding: 5px;
}
nav a {
  color: green;
  font-size: 20px;
  font-weight: bold;
  text-decoration: none;
}
nav a:hover {
  color: rgb(1, 189, 1);
  text-decoration: line-through;
}
</style>
