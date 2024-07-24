<script setup></script>
<template> header class="font-bold text-xl text-center">
    <header>
        <h1>Formulário de Usuário</h1>
    </header>
    <hr />
    <main>
        <form @submit.prevent="enviarFormulario"
            class="m-auto bg-slate-400 border-2 border-black flex flex-col flex-wrap text-lg shadow-md shadow-inner size-6/12 p-10 rounded-md">

            <template>
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
                <option v-for="(estado, index) in estados" :key="index" :value="estado.id">
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
            <button @submit="enviarFormulario">Enviar Formulario</button>
</template>
</form>
</main>
</template>
<style scoped></style>