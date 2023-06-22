<script setup>
import HelloWorld from './components/HelloWorld.vue'

const names = ['C++', 'Python', 'Java', 'Vue']
import BaseInput from './BaseInput.vue'

const saveValue = value => {
  alert(value)
}

const hideItem = () => {
  const p = document.querySelector('p')
  p.style.display = 'none'
}
const showItem = () => {
  const p = document.querySelector('p')
  p.style.display = 'block'
}



</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
  </header>
  <div>
  <h1>Ejemplo v-for</h1>
  
  <li v-for="(n, key) in names" :key="key">
    {{ `${key} -> ${n}` }}
  </li>
  </div>

  <div>
    <h1>Ejemplo Componentes</h1>
  <BaseInput @update="saveValue"/>
  </div>

  <div>
    <h1>Prueba v-if</h1>
  <p>
    Texto de prueba que quiero ocultar o mostrar
  </p>
  <button @click="showItem">
    mostrar texto
  </button>
  <button @click="hideItem">
    ocultar texto
  </button>
  </div>

</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
