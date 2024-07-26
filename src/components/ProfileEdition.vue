<script setup>
import { reactive, ref, useSSRContext } from 'vue';

const user = reactive({
    nome: "",
    email: "",
    senha: "",
    dataNascimento: "",
    endereco: "",
    cidade: "",
    estado: "",
    hobby: [],
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
    { name: 'Mato Grosso do Sul', id: 'MS' },
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
const hob = ref
const lingProg = ref([]);


</script>
<template>
    <form
        class="m-auto bg-slate-400 border-2 border-black flex flex-col flex-wrap text-lg shadow-md shadow-inner size-6/12 p-10 rounded-md"
        @submit.prevent="$emit('salvar', { ...user })">
        <label class="" for="nome">Nome:</label>
        <input class="rounded-md p-1" type="text" id="nome" v-model="user.nome" minlength="3" />

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

        <p> Hobbies </p>
        <input type="checkbox" id="jogos" value="jogos" v-model="user.hobby" />
        <label for="jogos">Jogos</label>
        
        <input type="checkbox" id="artes" value="artes" v-model="user.hobby" />
        <label for="artes">Artes</label>
        
        <input type="checkbox" id="musica" value="musica" v-model="user.hobby" />
        <label for="musica">Música</label>

        <input type="checkbox" id="escrever" value="escrever" v-model="user.hobby">
        <label for="escrever">Escrever</label>

        <input type="checkbox" id="ler" value="ler" v-model="user.hobby">
        <label for="ler">Ler</label>

        <div class="language-options">
            <p>Linguagem:</p>
            <label for="java">Java</label>
            <input type="radio" id="java" value="java" v-model="user.lingProg" />

            <label for="js">JavaScript</label>
            <input type="radio" id="js" value="js" v-model="user.lingProg" />

            <label for="c">C</label>
            <input type="radio" id="c" value="c" v-model="user.lingProg" />

            <label for="python">Python</label>
            <input type="radio" id="python" value="python" v-model="user.lingProg" />

            <label for="sql">SQL</label>
            <input type="radio" id="sql" value="SQL" v-model="user.lingProg" />
            
            <label for="css">CSS</label>
            <input type="radio" id="css" value="css" v-model="user.lingProg" />
        </div>

        <label for="">Biografia:</label>
        <input class="rounded-md p-1" type="text" id="bio" v-model="user.bio" width="100" />
        <button type="submit">Enviar Formulario</button>
    </form>
</template>
<style scoped></style>