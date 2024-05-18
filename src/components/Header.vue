<template>
  <header>
    <router-link to="/">Main</router-link>
    <router-link to="/fantasy">Fantasy</router-link>
    <router-link to="/royale">Royale</router-link>
    <router-link to="/rpg">Rpg</router-link>
    <router-link to="/shooter">Shooter</router-link>
    <router-link to="/strategy">Strategy</router-link>
  </header>
</template>

<style scoped>
header {
  display: flex;
  justify-content: space-evenly;
  padding: 20px;
  font-size: 30px;
  color: #606361;
  background: #0c0913;
}
router-link-active {
    color: white;
}
</style>
