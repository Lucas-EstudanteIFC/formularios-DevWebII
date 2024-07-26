<script setup>
import { reactive, ref } from 'vue';

const user = reactive ({
    nome: "",
    email: "",
    senha: "",
    dataNascimento: "",
    endereco: "",
    cidade: "",
    estado: "",
    hobby: "",
    lingProg: "",
    bio: "",

});

const estados = [
    { name: 'Acre', id: 'AC' },
    { name: 'Alagoas', id: 'AL' },
    { name: 'Amapá', id: 'AP' },
    { name: 'Amazonas', id: 'AM' },
    { name: 'Bahia', id: 'BA' },
    { name: 'Ceará', id: 'CE' },
    { name: 'Distrito Federal', id: 'DF' },
    { name: 'Espírito Santo', id: 'ES' },
    { name: 'Goiás', id: 'GO' },
    { name: 'Maranhão', id: 'MA' },
    { name: 'Mato Grosso', id: 'MT' },
    { name: 'Mato Grosso do Su', id: 'MS' },
    { name: 'Minas Gerais', id: 'MG' },
    { name: 'Pará', id: 'PA' },
    { name: 'Paraíba', id: 'PB' },
    { name: 'Paraná', id: 'PR' },
    { name: 'Pernambuco', id: 'PE' },
    { name: 'Piauí', id: 'PI' },
    { name: 'Rio de Janeiro', id: 'RJ' },
    { name: 'Rio Grande do Norte', id: 'RN' },
    { name: 'Rio Grande do Sul', id: 'RS' },
    { name: 'Rondônia', id: 'RO' },
    { name: 'Roraima', id: 'RR' },
    { name: 'Santa Catarina ', id: 'SC' },
    { name: 'São Paulo', id: 'SP' },
    { name: 'Sergipe', id: 'SE' },
    { name: 'Tocantins', id: 'TO' }
];

const listaHobbies = [
    { nome: 'Escrever', id: 1 },
    { nome: 'Ler', id: 2 },
    { nome: 'Esportes', id: 3 },
    { nome: 'Passeios', id: 4 },
    { nome: 'Colecionar', id: 5 },
    { nome: 'Video-games', id: 6 }
];

const listaProg = [
    { id: 1, nome: 'Python' },
    { id: 2, nome: 'Javascript' },
    { id: 3, nome: 'SQL' },
    { id: 4, nome: 'CSS' },
    { id: 5, nome: 'C#' },
    { id: 6, nome: 'HTML' }
];

const hob = ref([]);
const lingProg = ref([]);


</script>
<template>
    <form class="m-auto bg-slate-400 border-2 border-black flex flex-col flex-wrap text-lg shadow-md shadow-inner size-6/12 p-10 rounded-md" @submit.prevent="$emit('salvar', {...user})">
            <label class="" for="nome">Nome:</label>
            <input class="rounded-md p-1" type="text" id="nome" v-model="user.nome" minlength="10" />

            <label for="email">Email:</label>
            <input class="rounded-md p-1" type="email" id="email" v-model="user.email" />

            <label for="senha">Senha:</label>
            <input class="rounded-md p-1" type="password" id="senha" v-model="user.senha" minlength="7" />

            <label for="data">Data de Nascimento:</label>
            <input class="rounded-md p-1" type="date" id="data" v-model="user.dataNascimento" />

            <label for="endereco">Endereço:</label>
            <input class="rounded-md p-1" type="number" id="endereco" v-model="user.endereco" />

            <label for="cidade">Cidade:</label>
            <input class="rounded-md p-1" type="text" id="cidade" v-model="user.cidade" />

            <label for="estado">Estado:</label>
            <select class="rounded-md p-1" name="estados" id="estado" v-model="user.estado">
                <option disabled value=""></option>
                <option v-for="estado in estados" :value="estado.name">
                    {{ estado.id }}
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
            <input class="rounded-md p-1" type="text" id="bio" v-model="user.bio" width="100" />
            <button type="submit" >Enviar Formulario</button>
    </form>
</template>
<style scoped></style>