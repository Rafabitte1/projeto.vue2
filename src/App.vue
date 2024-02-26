<script setup>
import {ref} from 'vue'


    const nome = 'Rafael'
    const idade = 17

    function inverter(texto) {
        return texto.split('').reverse().join('')
        
    }

    function saudacao() {
        return `Olá, ${nome}!`
    };


    const contador = ref(0)

function decrementar(){
  contador.value--
  if (contador.value < 0) {
    contador.value = 0
    alert(`Não pode ser menor do que zero`)
  }
   
}


function encrementar(){
  contador.value++

}




function resetar(){
contador.value = 0}

  const html = '<span style=color:red>  valor menor do que 10</span> ';

</script>

<template>
    <div class="info">
        <h1>Exemplo 1 - Mostrando informações na tela</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <hr />
        <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
        <p>O nome tem {{ nome.length }}  caracteres</p>
        <p>O nome invertido é: {{ inverter(nome) }} </p>
        <hr />
        <p> Exemplo de saudação usando função</p>
        <p> {{ saudacao() }}  </p>
    </div>
    <div class="contador">
      <button @click="encrementar">+</button>
<button @click="decrementar">-</button>
<p>O valor do contador é:{{ contador }}</p>
<button @click="resetar">resert</button>

    </div>
    <div>
    <span v-html="html"></span> 
    </div>
</template>

<style scoped>
.info {
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}
.contador{
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}
</style>