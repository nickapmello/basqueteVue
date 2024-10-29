<template>
  <div class="container">
    <header>
      <div class="logo-container">
        <img alt="Logo de basquete" class="logo" src="./assets/logobasket.png" />
      </div>
    </header>
    <main>
      <BasketballList />
    </main>
  </div>
</template>

<script setup>
import BasketballList from './components/BasketballList.vue';
</script>

<style scoped>
.container {
  font-family: 'Helvetica Neue', Arial, sans-serif;
  color: #ffffff;
  background-color: #121212;
  width: 800px;
  padding: 20px;
  border-radius: 10px;
  margin: 50px auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
