<script setup>
import { ref } from 'vue'
import ProfileEdition from './components/ProfileEdition.vue';
import ShowProfile from './components/ShowProfile.vue';

const troca = ref(false);
const resultado = ref({});

function salvar(dados) {
  resultado.value = dados;
  troca.value = !troca.value;
}

</script>

<template >
  <header class="font-bold text-xl text-center">
    <h1>Perfil de Usuário</h1>
  </header>

  <profile-edition @salvar="salvar"/>
  <show-profile :resultado="resultado" />
</template>
