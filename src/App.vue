<script setup>
  import { ref } from 'vue'

const nome = ref('');
const email = ref('');
const senha = ref('');
const senhaConfirmacao = ref('');
const dataDeNascimento = ref('');
const endereco = ref(''); 
const cidade = ref('');
const hobbies = ref('');
const liguagensDeProgramacao = ref('');
const biografia = ref('');

const estados = [
  { sigla: 'AC', nome: 'Acre' },
  { sigla: 'AL', nome: 'Alagoas' },
  { sigla: 'AP', nome: 'Amapá' },
  { sigla: 'AM', nome: 'Amazonas' },
  { sigla: 'BA', nome: 'Bahia' },
  { sigla: 'CE', nome: 'Ceará' },
  { sigla: 'DF', nome: 'Distrito Federal' },
  { sigla: 'ES', nome: 'Espírito Santo' },
  { sigla: 'GO', nome: 'Goiás' },
  { sigla: 'MA', nome: 'Maranhão' },
  { sigla: 'MT', nome: 'Mato Grosso' },
  { sigla: 'MS', nome: 'Mato Grosso do Sul' },
  { sigla: 'MG', nome: 'Minas Gerais' },
  { sigla: 'PA', nome: 'Pará' },
  { sigla: 'PB', nome: 'Paraíba' },
  { sigla: 'PR', nome: 'Paraná' },
  { sigla: 'PE', nome: 'Pernambuco' },
  { sigla: 'PI', nome: 'Piauí' },
  { sigla: 'RJ', nome: 'Rio de Janeiro' },
  { sigla: 'RN', nome: 'Rio Grande do Norte' },
  { sigla: 'RS', nome: 'Rio Grande do Sul' },
  { sigla: 'RO', nome: 'Rondônia' },
  { sigla: 'RR', nome: 'Roraima' },
  { sigla: 'SC', nome: 'Santa Catarina' },
  { sigla: 'SP', nome: 'São Paulo' },
  { sigla: 'SE', nome: 'Sergipe' },
  { sigla: 'TO', nome: 'Tocantins' }
];
</script>

<template>
  <div>
    <div class="card mb-5 mt-5">
      <div class="card-header text-center">
        <h1>Formulário</h1>
      </div>
      <div class="card-body">
        <h2 class="card-title">Insira os dados:</h2>

        <div class="form-group">
          <label for="nome">Nome:</label>
          <input type="text" v-model="nome" class="form-control" id="nome" placeholder="Nome" required>
        </div>

        <div class="form-group">
          <label for="email">Email:</label>
          <input type="email" v-model="email" class="form-control" id="email" placeholder="Email" required>
        </div>

        <div class="form-group">
          <label for="senha">Senha:</label>
          <input type="password" v-model="senha" class="form-control" id="senha" placeholder="Senha" required>
        </div>

        <div class="form-group">
          <label for="senha-confirmacao">Confirme a Senha:</label>
          <input type="password" v-model="senhaConfirmacao" class="form-control" id="senha-confirmacao" placeholder="Confirmação De Senha" required>
        </div>

        <div class="form-group">
          <label for="dataDeNascimento">Data de Nascimento:</label>
          <input type="date" v-model="dataDeNascimento" class="form-control" id="dataDeNascimento" placeholder="Data de Nascimento" required>
        </div>

        <div class="form-group">
        <label for="endereco">Endereço:</label>
         <input type="text" v-model="endereco" id="endereco" name="endereco" class="form-control" placeholder="Endereço" required>
        </div>

        <div class="form-group">
          <label for="cidade">Cidade:</label>
          <input type="text" v-model="cidade" class="form-control" id="cidade" placeholder="Cidade" required>
        </div>

        <div class="form-group">
          <label for="estado">Estado:</label>
          <select id="estado" v-model="selectedState" class="form-control" required>
            <option value="" disabled>Selecione um estado</option>
            <option v-for="(estado, index) in estados" :key="index" :value="estado.sigla">{{ estado.sigla }} - {{ estado.nome }}</option>
          </select>
        </div>

        <div class="form-group">
          <label for="hobbies">Hobbies:</label>
          <input type="text" v-model="hobbies" id="hobbies" name="Hobbies" class="form-control" placeholder="Hobbies"  required>
        </div>
        <div class="form-group">
        <label for="liguagensDeProgramacao">Liguagens de Programação:</label>
         <input type="text" v-model="liguagensDeProgramacao" id="liguagensDeProgramacao" name="Liguagens de Programacao" class="form-control" placeholder="Linguagens de Programação"  required>
        </div>
        <div class="form-group">
        <label for="biografia">Biografia:</label>
        <textarea v-model="biografia" name="biografia" id="biografia" cols="70" rows="6" class="form-control" placeholder="Biografia"></textarea>
      </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
