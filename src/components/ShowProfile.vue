<script setup>
 // Props para receber os dados
 // Vai receber um objeto
 // Mostrar num div sem form

import { ref } from 'vue'
defineProps(['resultado'])

const troca = ref(true)
function voltar() {
  resultado.value = {};
  troca.value = !troca.value;
}

</script>
<template>
    <div class="m-auto bg-slate-400 border-2 border-black flex flex-col flex-wrap text-lg shadow-md shadow-inner size-6/12 p-10 rounded-md">
      <h1>Resultado</h1>
      <p>Nome: {{ resultado.nome }}</p>
      <p>Email: {{ resultado.email }}</p>
      <p>Senha{{ resultado.senha }}</p>
      <p>Data de Nascimento{{ resultado.dataNascimento }}</p>
      <p>Endereço: {{ resultado.endereco }}</p>
      <p>Cidade: {{ resultado.cidade }}</p>
      <p>Estado: {{ resultado.estado }}</p>
      <p>{{ resultado.hobby }}</p>
      <p>{{ resultado.lingProg }}</p>
      <p>{{ resultado.bio }}</p>
      <button @click="voltar"></button>
    </div>
</template>
<style scoped>
</style>