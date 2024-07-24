<script setup>

</script>
<template>
    <form class="m-auto bg-slate-400 border-2 border-black flex flex-col flex-wrap text-lg shadow-md shadow-inner size-6/12 p-10 rounded-md">
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
        <button>Retornar a página</button>
    </form>
</template>
<style scoped>
</style>