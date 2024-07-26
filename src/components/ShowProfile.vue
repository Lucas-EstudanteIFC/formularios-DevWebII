<script setup>
 // Props para receber os dados
 // Vai receber um objeto
 // Mostrar num div sem form
defineProps(['resultado'])
</script>
<template>
    <div>
      <h1>Resultado</h1>
      <p>{{ resultado.nome }}</p>
    </div>
</template>
<style scoped>
</style>