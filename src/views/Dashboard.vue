/* eslint-disable */
<template>
 <nav class="navbar">
      <div class="container navbar-content">
          <h1>Qué parte del Mundo?</h1>
           <button @click="dark" class="btn-dark-mode">
                <i class="far fa-moon"></i>
                Dark Mode
            </button>
      </div>
  </nav>

  <header class="container filter-content my-2">
      <form class="form-search" id="formulario">
          <i class="fas fa-search"></i>
          <input type="text" placeholder="Ingresa País" id="inputFormulario">
      </form>
      <div class="custom-select" style="width:200px;">
          <select>
              <option value="">Filtrar por Región</option>
              <option value="">Todos</option>
              <option value="Africa">África</option>
              <option value="Americas">America</option>
              <option value="Asia">Asia</option>
              <option value="Europe">Europa</option>
              <option value="Oceania">Oceania</option>
          </select>
      </div>
  </header>

   <main class="container grid" id="banderas">
    </main>

   

  <a href="/">
      Home...
  </a>
 
</template>


<script>
import { collapsed, toggleSidebar } from '@/components/sidebar/state'
import './css/custom-select.css'
import './css/main.css'
import './css/normalize.css'

export default {
  
  data() {
    return {
      
      }
  },
  methods: {
    dark(){
      const btnDark = document.querySelector('.btn-dark-mode');
    
      btnDark.addEventListener('click', () => {
          console.log('diste click')
          document.body.classList.toggle('dark-mode');
      
          if (document.body.className === 'dark-mode') {
              btnDark.innerHTML = `
              <i class="far fa-sun"></i>
              Light Mode
              `
          } else {
              btnDark.innerHTML = `
              <i class="far fa-moon"></i>
              Dark Mode
              `
          }
      })
    }
  },
  setup() {
    return { collapsed, toggleSidebar }
  },
}
</script>
