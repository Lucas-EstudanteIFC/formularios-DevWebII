<script setup>
import { ref } from 'vue'

const mostrarResultado = ref(false);

const nome = ref('');
const email = ref('');
const senha = ref('');
const data = ref('');
const endereco = ref('');
const cidade = ref('');
const hob = ref([]);
const lingProg = ref([]);
const estados = [
  { id: 'Acre', name: 'AC' },
  { id: 'Alagoas', name: 'AL' },
  { id: 'Amapá', name: 'AP' },
  { id: 'Amazonas', name: 'AM' },
  { id: 'Bahia', name: 'BA' },
  { id: 'Ceará', name: 'CE' },
  { id: 'Distrito Federal', name: 'DF' },
  { id: 'Espírito Santo', name: 'ES' },
  { id: 'Goiás', name: 'GO' },
  { id: 'Maranhão', name: 'MA' },
  { id: 'Mato Grosso', name: 'MT' },
  { id: 'Mato Grosso do Su', name: 'MS' },
  { id: 'Minas Gerais', name: 'MG' },
  { id: 'Pará', name: 'PA' },
  { id: 'Paraíba', name: 'PB' },
  { id: 'Paraná', name: 'PR' },
  { id: 'Pernambuco', name: 'PE' },
  { id: 'Piauí', name: 'PI' },
  { id: 'Rio de Janeiro', name: 'RJ' },
  { id: 'Rio Grande do Norte', name: 'RN' },
  { id: 'Rio Grande do Sul', name: 'RS' },
  { id: 'Rondônia', name: 'RO' },
  { id: 'Roraima', name: 'RR' },
  { id: 'Santa Catarina ', name: 'SC' },
  { id: 'São Paulo', name: 'SP' },
  { id: 'Sergipe', name: 'SE' },
  { id: 'Tocantins', name: 'TO' }
]
const listaHobbies = [
  { nome: 'Escrever', id: 1 },
  { nome: 'Ler', id: 2 },
  { nome: 'Esportes', id: 3 },
  { nome: 'Passeios', id: 4 },
  { nome: 'Colecionar', id: 5 },
  { nome: 'Video-games', id: 6 }
]
const listaProg = [
  { id: 1, nome: 'Python' },
  { id: 2, nome: 'Javascript' },
  { id: 3, nome: 'SQL' },
  { id: 4, nome: 'CSS' },
  { id: 5, nome: 'C#' },
  { id: 6, nome: 'HTML' }
]

const bio = ref('')

function enviarFormulario() {
  if (
    nome.value == '' ||
    email.value == '' ||
    senha.value == '' ||
    data.value == '' ||
    endereco.value == '' ||
    cidade.value == '' ||
    estados.value == ''
  ) {
    alert(`Campo vazio detectado. Por favor, preencha-o`)
    return
  } else {
    mostrarResultado.value = !mostrarResultado.value
  }
}
</script>

<template>
  <header class="font-bold text-xl text-center">
    <h1>Formulário de Usuário</h1>
  </header>
  <hr />
  <main>
    <form
      @submit.prevent="enviarFormulario"
      class="m-2 bg-slate-400 border-2 border-black flex flex-col flex-wrap text-lg shadow-md shadow-inner"
    >
      <template v-if="!mostrarResultado">
        <label class="" for="nome">Nome:</label>
        <input type="text" id="nome" v-model="nome" minlength="10" />

        <label for="email">Email:</label>
        <input type="email" id="email" v-model="email" />

        <label for="senha">Senha:</label>
        <input type="password" id="senha" v-model="senha" minlength="7" />

        <label for="data">Data de Nascimento:</label>
        <input type="date" id="data" v-model="data" />

        <label for="endereco">Endereço:</label>
        <input type="number" id="endereco" v-model="endereco" />

        <label for="cidade">Cidade:</label>
        <input type="text" id="cidade" v-model="cidade" />

        <label for="estado">Estado:</label>
        <select name="estados" id="estado" v-model="estado">
          <option disabled value=""></option>
          <option v-for="(estado, index) in estados" :key="index" :value="estado.id">
            {{ estado.name }}
          </option>
        </select>

        <label for="">Hobbies:</label>
        <template v-for="hobby in listaHobbies" :key="hobby.id">
          <input type="checkbox" v-model="hob" :value="hobby.nome" />
          {{ hobby.nome }}
        </template>

        <label for="">Linguagens de Programação:</label>
        <template v-for="progs in listaProg" :key="progs.id">
          <input type="radio" v-model="lingProg" :value="progs.nome" />
          {{ progs.nome }}
        </template>

        <label for="">Biografia:</label>
        <input type="text" id="bio" v-model="bio" width="100" />
        <button @submit="enviarFormulario">Enviar Formulario</button>
      </template>

      <template v-else>
        <label>Nome: {{ nome }}</label>
        <label>Email: {{ email }}</label>
        <label>Senha: {{ senha }}</label>
        <label>Data de Nascimento: {{ data }}</label>
        <label>Endereço: {{ endereco }}</label>
        <label>Cidade: {{ cidade }}</label>
        <label>
          Estado:
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
        </label>
        <label>Hobbies: {{ hob }}</label>
        <label>Linguagens de Programação: {{ lingProg }}</label>
        <button @click="enviarFormulario">Retornar a página</button>
      </template>
    </form>
  </main>
</template>
