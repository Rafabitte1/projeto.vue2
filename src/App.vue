<script setup>
import { ref } from 'vue'

const nome = 'Rafael'
const idade = '17'

function inverter(texto) {
    return texto.split('').reverse().join('').toUpperCase()
}

function saudacao() {
    return `Olá, ${nome}!`
};

const contador = ref(0)

function decrementar() {
  contador.value--
  if (contador.value < 0) {
    contador.value = 0
    
  }
}

function encrementar() {
  contador.value++
}

function resetar() {
  contador.value = 0
}


</script>

<template>
  <div>
    <div class="info">
      <h1>Exemplo 1 - Mostrando informações na tela</h1>
      <p>Nome: {{ nome }} </p>
      <p>Idade: {{ idade }}  anos</p>
      <hr />
      <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
      <p>O nome tem {{ nome.length }}  caracteres</p>
      <p>O nome invertido em letras maiúsculas é: {{ inverter(nome) }} </p>
      <hr />
      <p> Exemplo de saudação usando função</p>
      <p> {{ saudacao() }}  </p>
    </div>
    <div class="contador">
      <h1>Contador</h1>
      <button @click="encrementar">+</button>
      <button @click="decrementar">-</button>
      <p>O valor do contador é: {{ contador }}</p>
      <button @click="resetar">reset</button>
      <div
      :style="{ backgroundColor: contador > 10 ? 'green' : 'red' }"
    >
      <p v-if="contador > 10">Valor maior que 10</p>
      <p v-else>Valor menor que 10</p>
    </div>
    </div>
    
  </div>
</template>

<style scoped>

.info {
  background-color: rgba(13, 12, 35, 1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
  margin-bottom: 20px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}

.contador {
  background-color: rgba(28, 56, 87, 1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}

.custom-button {
  background-color: rgba(47, 58, 130, 1);
  color: white;
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
  margin-right: 10px;
}

.custom-button:hover {
  background-color: rgba(33, 49, 114, 1);
}

.custom-button:active {
  background-color: rgba(47, 58, 130, 1);
}

.contador > div {
  padding: 15px;
  margin-top: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
.contador > div > p {
  margin: 0;
}


.contador > div > p:nth-child(2) {
  display: none;
}


.contador > div > p:nth-child(2) + p {
  display: none;
}
</style>
