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
    estados.value == '' ||
    hob.value == [] ||
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

</template>
