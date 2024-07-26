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
      <p>{{ resultado.nome }}</p>
      <p>{{ resultado.email }}</p>
      <p>{{ resultado.senha }}</p>
      <p>{{ resultado.dataNascimento }}</p>
      <p>{{ resultado.endereco }}</p>
      <p>{{ resultado.cidade }}</p>
      <p>{{ resultado.estado }}</p>
      <p>{{ resultado.hobby }}</p>
      <p>{{ resultado.lingProg }}</p>
      <p>{{ resultado.bio }}</p>
      <button @click="voltar"></button>
    </div>
</template>
<style scoped>
</style>