<script setup>
import { ref } from 'vue'

const nome = ref('')
const email = ref('')
const senha = ref('')
const data = ref('')
const endereco = ref('')
const cidade = ref('')
const estado = ref('')
const hobbies = ref([
  {
    id: 1,
    nome: 'Escrever'
  },
  {
    id: 2,
    nome: 'Ler'
  },
  {
    id: 3,
    nome: 'Esportes'
  },
  {
    id: 4,
    nome: 'Passeios'
  },
  {
    id: 5,
    nome: 'Colecionar'
  },
  {
    id: 6,
    nome: 'Video-games'
  }
])
const lingProg = ref([  {
    id: 1,
    nome: 'Python'
  },
  {
    id: 2,
    nome: 'Javascript'
  },
  {
    id: 3,
    nome: 'SQL'
  },
  {
    id: 4,
    nome: 'CSS'
  },
  {
    id: 5,
    nome: 'C#'
  },
  {
    id: 6,
    nome: 'HTML'
  }])
const bio = ref('')
const mostrarResultado = ref(false)

function enviarFormulario() {
  if (
    nome.value == '' ||
    email.value == '' ||
    senha.value == '' ||
    data.value == '' ||
    endereco.value == '' ||
    cidade.value == '' ||
    estado.value == '' ||
    hobbies.value == [] ||
    lingProg.value == []
  ) {
    alert(`Campo vazio detectado. Por favor, preencha-o`)
    return
  } else {
    mostrarResultado.value = !mostrarResultado.value
  }
}
</script>

<template>
  <header><h1>Formulário de Usuário</h1></header>
  <hr />
  <main>
    <form @submit.prevent="enviarFormulario" v-if="!mostrarResultado" class="formulario container">
      <label for="nome">Nome</label>
      <input type="text" id="nome" v-model="nome" minlength="10" />

      <label for="email">Email</label>
      <input type="email" id="email" v-model="email" />

      <label for="senha">Senha</label>
      <input type="password" id="senha" v-model="senha" minlength="7" />

      <label for="data">Data de Nascimento</label>
      <input type="date" id="data" v-model="data" />

      <label for="endereco">Endereço</label>
      <input type="number" id="endereco" v-model="endereco" />

      <label for="cidade">Cidade</label>
      <input type="text" id="cidade" v-model="cidade" />

      <label for="estado">Estado</label>
      <select name="estados" id="estado" v-model="estado">
        <option value=""></option>
        <option value="AC">AC</option>
        <option value="AL">AL</option>
        <option value="AP">AP</option>
        <option value="AM">AM</option>
        <option value="BA">BA</option>
        <option value="CE">CE</option>
        <option value="DF">DF</option>
        <option value="ES">ES</option>
        <option value="GO">GO</option>
        <option value="MA">MA</option>
        <option value="MT">MT</option>
        <option value="MS">MS</option>
        <option value="MG">MG</option>
        <option value="PA">PA</option>
        <option value="PB">PB</option>
        <option value="PR">PR</option>
        <option value="PE">PE</option>
        <option value="PI">PI</option>
        <option value="RJ">RJ</option>
        <option value="RN">RN</option>
        <option value="RS">RS</option>
        <option value="RO">RO</option>
        <option value="RR">RR</option>
        <option value="SC">SC</option>
        <option value="SP">SP</option>
        <option value="SE">SE</option>
        <option value="TO">TO</option>
      </select>

      <label for="">Hobbies</label>
      <div v-for="hobby in hobbies" :key="hobby.id">
        <input type="checkbox" v-model="hobbies" :value="hobby.id" />
        {{ hobby.nome }}
      </div>

      <label for="">Linguagens de Programação</label>
      <div v-for="progs in lingProg" :key="progs.id">
        <input type="checkbox" v-model="lingProg" :value="progs.id" />
        {{ progs.nome }}</div>

      <label for="">Biografia</label>
      <input type="text" id="bio" v-model="bio"/>
      <button @submit="enviarFormulario"></button>
    </form>

    <div v-else>
      <p>Nome: {{ nome }}</p>
      <p>Email: {{ email }}</p>
      <p>Senha: {{ senha }}</p>
      <p>Data de Nascimento: {{ data }}</p>
      <p>Endereço: {{ endereco }}</p>
      <p>Cidade: {{ cidade }}</p>
      <p>
        Estado
        {{
          estado
            .replace('AC', 'Acre')
            .replace('AL', 'Alagoas')
            .replace('AP', 'Amapá')
            .replace('AM', 'Amazonas')
            .replace('BA', 'Bahia')
            .replace('CE', 'Ceará')
            .replace('DF', 'Distrito Federal')
            .replace('ES', 'Espírito Santo')
            .replace('GO', 'Goiás')
            .replace('MA', 'Maranhão')
            .replace('MT', 'Mato')
            .replace('MS', 'Mato Grosso do Sul')
            .replace('MG', 'Minas Gerais')
            .replace('PA', 'Pará')
            .replace('PR', 'Paraná')
            .replace('PB', 'Paraíba')
            .replace('PE', 'Pernambuco')
            .replace('PI', 'Piauí')
            .replace('RJ', 'Rio de Janeiro')
            .replace('RN', 'Rio Grande do Norte')
            .replace('RS', 'Rio Grande do Sul')
            .replace('RO', 'Rondônia')
            .replace('RR', 'Roraima')
            .replace('SC', 'Santa Catarina')
            .replace('SP', 'São Paulo')
            .replace('SE', 'Sergipe')
            .replace('TO', 'Tocantins')
        }}
      </p>
      <p>Hobbies: {{ hobbies }}</p>
      <p>Linguagens de Programação: {{ lingProg }}</p>
    </div>
  </main>
</template>

<style scoped>
form > * {
  display: block;
}
</style>
