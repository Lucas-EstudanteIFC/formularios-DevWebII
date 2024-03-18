<script setup>
import { ref } from 'vue'

const nome = ref('')
const email = ref('')
const senha = ref('')
const data = ref('')
const endereço = ref('')
const cidade = ref('')
const estado = ref('')
const hobbies = ref([])
const lingProg = ref([])
const bio = ref('')
</script>

<template>
  <header>Formulário de Usuário</header>

  <main>
    <label for="nome">Nome</label>
    <input type="text" id="nome" v-model="nome" minlength="30" />

    <label for="email">Email</label>
    <input type="email" id="email" v-model="email"/>

    <label for="senha">Senha</label>
    <input type="password" id="senha" minlength="7"/>

    <label for="data">Data de Nascimento</label>
    <input type="date" id="data"/>

    <label for="endereco">Endereço</label>
    <input type="number" id="endereco"/>

    <label for="cidade">Cidade</label>
    <input type="text" />
  
    <label for="estado">Estado</label>
    <input type="select" />
  
    <label for="hobbies">Hobbies</label>
    <input type="text" />

    <label for="">Linguagens de Programação</label>
    <input type="checkbox" />
    <input type="checkbox" />
    <input type="checkbox" />
    <input type="checkbox" />
    <input type="checkbox" />
    <input type="checkbox" />

    <label for="bio">Biografia</label>
    <input type="text"/>
  </main>
</template>

<style scoped>
</style>
