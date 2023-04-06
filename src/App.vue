<script setup>
  import { ref } from 'vue'

const nome = ref('');
const email = ref('');
const senha = ref('');
const senhaConfirmacao = ref('');
const mostrarSenha = ref(false);
const dataDeNascimento = ref('');
const endereco = ref(''); 
const cidade = ref('');
const hobbies = ref('');
const liguagensDeProgramacao = ref('');
const biografia = ref('');

const estados = [
  { sigla: 'AC', nomeEstado: 'Acre' },
  { sigla: 'AL', nomeEstado: 'Alagoas' },
  { sigla: 'AP', nomeEstado: 'Amapá' },
  { sigla: 'AM', nomeEstado: 'Amazonas' },
  { sigla: 'BA', nomeEstado: 'Bahia' },
  { sigla: 'CE', nomeEstado: 'Ceará' },
  { sigla: 'DF', nomeEstado: 'Distrito Federal' },
  { sigla: 'ES', nomeEstado: 'Espírito Santo' },
  { sigla: 'GO', nomeEstado: 'Goiás' },
  { sigla: 'MA', nomeEstado: 'Maranhão' },
  { sigla: 'MT', nomeEstado: 'Mato Grosso' },
  { sigla: 'MS', nomeEstado: 'Mato Grosso do Sul' },
  { sigla: 'MG', nomeEstado: 'Minas Gerais' },
  { sigla: 'PA', nomeEstado: 'Pará' },
  { sigla: 'PB', nomeEstado: 'Paraíba' },
  { sigla: 'PR', nomeEstado: 'Paraná' },
  { sigla: 'PE', nomeEstado: 'Pernambuco' },
  { sigla: 'PI', nomeEstado: 'Piauí' },
  { sigla: 'RJ', nomeEstado: 'Rio de Janeiro' },
  { sigla: 'RN', nomeEstado: 'Rio Grande do Norte' },
  { sigla: 'RS', nomeEstado: 'Rio Grande do Sul' },
  { sigla: 'RO', nomeEstado: 'Rondônia' },
  { sigla: 'RR', nomeEstado: 'Roraima' },
  { sigla: 'SC', nomeEstado: 'Santa Catarina' },
  { sigla: 'SP', nomeEstado: 'São Paulo' },
  { sigla: 'SE', nomeEstado: 'Sergipe' },
  { sigla: 'TO', nomeEstado: 'Tocantins' }
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
          <input type="checkbox" v-model="mostrarSenha" value="Sim">
        </div>

        <div class="form-group">
          <label for="senha-confirmacao">Confirme a Senha:</label>
          <input type="password" v-model="senhaConfirmacao" class="form-control" id="senhaConfirmacao" placeholder="Confirmação De Senha" required>
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
            <option v-for="(estado, index) in estados" :key="index" :value="estado.sigla">{{ estado.sigla }} - {{ estado.nomeEstado }}</option>
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

    <div class=" card mb-5 mt-5 " id="informacao">
      <div class="card-header text-center">
        <h1>Formulário</h1>
      </div>
      <div class="card-body">
        <h2 class="card-title">Seus dados:</h2>
      <div>
        <ul class="list-group list-group-flush">
    <label for="itemNome">Nome:</label>
    <li class="list-group-item">{{nome}}</li>
    <label for="itemNome">Email:</label>
    <li class="list-group-item">{{email}}</li>
    <label for="itemNome">Senha:</label>
    <li class="list-group-item">{{senha}}</li>
    <label for="itemNome">Confirmação:</label>
    <li class="list-group-item">{{senhaConfirmacao}}</li>
    <label for="itemNome">Data de Nascimento:</label>
    <li class="list-group-item">{{dataDeNascimento}}</li>
    <label for="itemNome">Endereço:</label>
    <li class="list-group-item">{{endereco}}</li>
    <label for="itemNome">Cidade:</label>
    <li class="list-group-item">{{cidade}}</li>
    <label for="itemNome">Estado:</label>
    <li class="list-group-item">{{ estados}}</li>
    <label for="itemNome">Hobbies:</label>
    <li class="list-group-item">{{hobbies}}</li>
    <label for="itemNome">Linguagens de Programação:</label>
    <li class="list-group-item">{{liguagensDeProgramacao}}</li>
    <label for="itemNome">Biografia:</label>
    <li class="list-group-item">{{biografia}}</li>
  </ul>
</div>
      </div>
    </div>
</template>

<style scoped>

</style>
