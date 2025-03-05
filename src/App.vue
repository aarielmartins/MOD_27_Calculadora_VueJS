<script setup>
import { reactive } from 'vue'
import Cabecalho from './components/Cabecalho.vue'
import Operacao from './components/Operacao.vue'
import Resultado from './components/Resultado.vue'

let estado = reactive({
  n1: "",
  n2: "",
  operacaoFinal:"0",
  operador: "+"
})

const numero1 = (evento) => {
  estado.n1 = parseFloat(evento.target.value)
  operacao()
}

const numero2 = (evento) => {
  estado.n2 = parseFloat(evento.target.value)
  operacao()
}

const mudaOperador = (evento) => {
  estado.operador = evento.target.value
  operacao()
}

const operacao = () => {

  switch(estado.operador){
    case "+":
      return estado.operacaoFinal = (estado.n1 + estado.n2)
    case "-":
      return estado.operacaoFinal = (estado.n1 - estado.n2)
    case "/":
      return estado.operacaoFinal = (estado.n1 / estado.n2)
    case "*":
      return estado.operacaoFinal = (estado.n1 * estado.n2)
  }

}
</script>

<template>
  <body class=" vh-100 w-100 d-flex justify-content-center align-items-center">
    <div class="container col-5 rounded-5 d-flex justify-content-center flex-column align-items-center">
      <Cabecalho/>
      <!-- <div class="row d-flex justify-content-center">
        <div class="col-10 d-flex flex-raw justify-content-around">
          <input type="number" required @keyup = "numero1" class="w-25 rounded-3 p-2">
          <select @change="mudaOperador" class="rounded-3 p-2">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="/">÷</option>
            <option value="*">×</option>
          </select>
          <input type="number" required @keyup = "numero2" class="w-25 rounded-3 p-2" >
        </div>
      </div> -->
      <Operacao :mudaOperador="mudaOperador" :numero1="numero1" :numero2="numero2"/>
      <Resultado :resultado="estado.operacaoFinal"/>
    </div>
  </body>
</template>

<style scoped>
  body{
    background-image: url('../src/images/fundo2.jpg');
    background-size: cover;
    color: white;
  }

  .container{
    background-color: rgba(255, 255, 255, 0.3);
  }
</style>