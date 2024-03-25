<script setup>
import { ref } from 'vue'

const nome = ref('')
const email = ref('')
const senha = ref('')
const data = ref('')
const endereco = ref('')
const cidade = ref('')
const estado = ref('')
const hobbies = ref([])
const lingProg = ref([])
const bio = ref('')

let troca = ref(false);

</script>

<template>
  <header><h1>Formulário de Usuário</h1></header>
  <hr />
  <main>
    <form action="">
      <label for="nome">Nome</label>
      <input type="text" id="nome" v-model="nome" minlength="30" />

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
      <input type="checkbox" id="hobbies" value="hobbie1" v-model="hobbies" />Hobbie 1
      <input type="checkbox" id="hobbies" value="hobbie2" v-model="hobbies" />Hobbie 2
      <input type="checkbox" id="hobbies" value="hobbie3" v-model="hobbies" />Hobbie 3
      <input type="checkbox" id="hobbies" value="hobbie4" v-model="hobbies" />Hobbie 4
      <input type="checkbox" id="hobbies" value="hobbie5" v-model="hobbies" />Hobbie 5
      <input type="checkbox" id="hobbies" value="hobbie6" v-model="hobbies" />Hobbie 6

      <label for="">Linguagens de Programação</label>
      <input type="checkbox" id="ling" v-model="lingProg" />
      <input type="checkbox" id="ling" v-model="lingProg" />
      <input type="checkbox" id="ling" v-model="lingProg" />
      <input type="checkbox" id="ling" v-model="lingProg" />
      <input type="checkbox" id="ling" v-model="lingProg" />
      <input type="checkbox" id="ling" v-model="lingProg" />

      <label for="bio">Biografia</label>
      <input type="text" id="bio" v-model="bio" />
      <button @click="troca"></button>
    </form>

    <div v-if="(troca = true)">
      <p>Nome: {{ nome }}</p>
      <p>Email: {{ email }}</p>
      <p>Senha: {{ senha }}</p>
      <p>Data de Nascimento: {{ data }}</p>
      <p>Endereço: {{ endereco }}</p>
      <p>Cidade: {{ cidade }}</p>
      <p>Estado {{ estado }}</p>
    </div>
  </main>
</template>

<style scoped>
form > * {
  display: block;
}
</style>
