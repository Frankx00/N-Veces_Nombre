<script setup>
import { ref } from 'vue';

const numero = ref(0); 
const texto = ref('');
const cadena = ref([]);

const agregar = () => {   //Para declarar valores dentro de un for es con let, y puse numero.value para que agarre el valor del numero
  for (let contador = 0; contador < numero.value; contador++) { 
    cadena.value.push(texto.value);
  }
}

const borrar=()=>{
  cadena.value=[];
}
</script>

<template>
  <div id="contenedor" class="container text-center">
    <h1 class="border-bottom border-top border-info border-4">N_VECES_TEXTO</h1>
    <div class="text-center">
      <div class="input-group flex-nowrap ">
        <div id="number" class="input-group flex-nowrap ">
          <span class="input-group-text border border-danger border-2" id="addon-wrapping"> # </span>
          <input type="number" class="form-control border-2 border-danger" v-model="numero" placeholder="Ingrese un numero" required aria-label="Username" aria-describedby="addon-wrapping">
        </div>
        <div id="text" class="input-group flex-nowrap">
          <span class="input-group-text border border-danger border-2 " id="addon-wrapping"> -> </span>
          <input type="text" class="form-control border-2 border-danger" v-model="texto" placeholder="Ingrese el texto" required aria-label="Username" aria-describedby="addon-wrapping">
        </div>
       <button class="btn btn-outline-primary" @click="agregar">GENERAR</button>
       <button class="btn btn-outline-danger" @click="borrar">BORRAR</button>
      </div>
    </div>
    <ul class="list-group mt-2">
      <li class="list-group-item list-group-item-primary" v-for="texto in cadena">
        {{ texto }}
      </li>
    </ul>
  </div>
</template>

<style>
#contenedor {
  height: 100vh;
  width: 50vw;
}
#number{
  margin: 5px;
}
#text{
  margin: 5px;
  margin-right: 10px;
}

button {
  margin: 7px;
}
</style>
