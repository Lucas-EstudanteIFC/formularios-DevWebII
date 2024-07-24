<script setup>
import { ref } from 'vue';

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

// [function enviarFormulario() {
//     if (
//         nome.value == '' ||
//         email.value == '' ||
//         senha.value == '' ||
//         data.value == '' ||
//         endereco.value == '' ||
//         cidade.value == '' ||
//         estados.value == '' ||
//         hob.value == [] ||
//         lingProg.value == []
//     ) {
//         alert(`Campo vazio detectado. Por favor, preencha-o`);
//         return
//     }
// }]


</script>
<template>
    <form class="m-auto bg-slate-400 border-2 border-black flex flex-col flex-wrap text-lg shadow-md shadow-inner size-6/12 p-10 rounded-md">
            <label class="" for="nome">Nome:</label>
            <input class="rounded-md p-1" type="text" id="nome" v-model="nome" minlength="10" />

            <label for="email">Email:</label>
            <input class="rounded-md p-1" type="email" id="email" v-model="email" />

            <label for="senha">Senha:</label>
            <input class="rounded-md p-1" type="password" id="senha" v-model="senha" minlength="7" />

            <label for="data">Data de Nascimento:</label>
            <input class="rounded-md p-1" type="date" id="data" v-model="data" />

            <label for="endereco">Endereço:</label>
            <input class="rounded-md p-1" type="number" id="endereco" v-model="endereco" />

            <label for="cidade">Cidade:</label>
            <input class="rounded-md p-1" type="text" id="cidade" v-model="cidade" />

            <label for="estado">Estado:</label>
            <select class="rounded-md p-1" name="estados" id="estado" v-model="estado">
                <option disabled value=""></option>
                <option v-for="(estado, index) in estados" :key="index" :v@submit="enviarFormulario" value="estado.id">
                    {{ estado.name }}
                </option>
            </select>

            <label for="">Hobbies:</label>
            <div v-for="hobby in listaHobbies" :key="hobby.id">
                {{ hobby.nome }}
                <input type="checkbox" v-model="hob" :value="hobby.nome" />

            </div>

            <label for="">Linguagens de Programação:</label>
            <div v-for="progs in listaProg" :key="progs.id">
                {{ progs.nome }}
                <input type="radio" v-model="lingProg" :value="progs.nome" />
            </div>

            <label for="">Biografia:</label>
            <input class="rounded-md p-1" type="text" id="bio" v-model="bio" width="100" />
            <button @click="$emit('salvar', {...ProfileEditionVue})">Enviar Formulario</button>
    </form>
</template>
<style scoped></style>