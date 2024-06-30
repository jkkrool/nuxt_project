<template>
    <h3>Strona główna</h3>
    <button @click="showAlert">Kliknij mnie</button>
    <button @click="showConsole">Kliknij mnie</button>
    <br/>
    <span v-if="showText">Pokaż tekst v-id</span><br/>
    <span v-show="showText">Pokaż tekst v-show</span>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const showText = ref(false)
  const showConsole = () => console.log("Dodałeś do koszyka ")
  const showAlert = () => {
    alert("Klik")
    showText.value = !showText.value
  }
  </script>
  