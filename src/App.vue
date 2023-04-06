<script setup>
  import { ref } from 'vue'

const informacaoCliente = ref({
  nome: '',
  email: '',
  senha: '',
  confirma: '',
  data: 0,
  endereco: '',
  cidade: '',
  estado: '',
  hobbies: '',
  linguagens: '',
  biografia: '',
})

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
]

const estadoSelecionado = ref('');

</script>

<template>
    <div class="card mb-5 mt-5">
      <div class="card-header text-center">
        <h1>Formulário</h1>
      </div>
      <div class="card-body">
        <h2 class="card-title">Insira os dados:</h2>

        <div class="form-group">
          <label for="informacaoCliente.nome">Nome:</label>
          <input type="text" v-model="informacaoCliente.nome" class="form-control" placeholder="Nome" required>
        </div>

        <div class="form-group">
          <label for="informacaoCliente.email">Email:</label>
          <input type="email" v-model="informacaoCliente.email" class="form-control" placeholder="Email" required>
        </div>

        <div class="form-group">
          <label for="informacaoCliente.senha">Senha:</label>
          <input type="password" v-model="informacaoCliente.senha" class="form-control" placeholder="Senha" required>
        </div>

        <div class="form-group">
          <label for="informacaoCliente.senhaConfirmacao">Confirme a Senha:</label>
          <input type="password" v-model="informacaoCliente.senhaConfirmacao" class="form-control" placeholder="Confirmação De Senha" required>
        </div>

        <div class="form-group">
          <label for="informacaoCliente.dataDeNascimento">Data de Nascimento:</label>
          <input type="date" v-model="informacaoCliente.dataDeNascimento" class="form-control" placeholder="Data de Nascimento" required>
        </div>

        <div class="form-group">
        <label for="informacaoCliente.endereco">Endereço:</label>
         <input type="text" v-model="informacaoCliente.endereco" name="endereco" class="form-control" placeholder="Endereço" required>
        </div>

        <div class="form-group">
          <label for="informacaoCliente.cidade">Cidade:</label>
          <input type="text" v-model="informacaoCliente.cidade" class="form-control" placeholder="Cidade" required>
        </div>

        <div>
    <div class="form-group">
      <label for="estadoSelecionado">Estado:</label>
      <select v-model="estadoSelecionado" class="form-control" required>
        <option value="" disabled>Selecione o estado</option>
        <option v-for="estado in estados" :key="estado.sigla" :value="estado.nomeEstado">{{ estado.sigla }}</option>
      </select>
    </div>

        <div class="form-group">
          <label for="informacaoCliente.hobbies">Hobbies:</label>
          <input type="text" v-model="informacaoCliente.hobbies" id="hobbies" name="Hobbies" class="form-control" placeholder="Hobbies"  required>
        </div>
        <div class="form-group">
        <label for="informacaoCliente.liguagensDeProgramacao">Liguagens de Programação:</label>
         <input type="text" v-model="informacaoCliente.liguagensDeProgramacao" id="liguagensDeProgramacao" name="Liguagens de Programacao" class="form-control" placeholder="Linguagens de Programação"  required>
        </div>
        <div class="form-group">
        <label for="informacaoCliente.biografia">Biografia:</label>
        <textarea v-model="informacaoCliente.biografia" name="biografia" cols="70" rows="6" class="form-control" placeholder="Biografia"></textarea>
      </div>
      
      </div>
    </div>
  </div>

    <div class=" card mb-5 mt-5 ">
      <div class="card-header text-center">
        <h1>Formulário</h1>
      </div>
      <div class="card-body">
        <h2 class="card-title">Seus dados:</h2>
      <div>
        <ul class="list-group list-group-flush">

      
    <label for="itemNome">Nome:</label>
    <div>
      <div class="form-group">
    <li class="list-group-item">{{ informacaoCliente.nome }}</li>
  </div>
</div>

    <label for="itemNome">Email:</label>
    <div>
      <div class="form-group">
    <li class="list-group-item">{{ informacaoCliente.email }}</li>
  </div>
</div>    

    <label for="itemNome">Senha:</label>
    <div>
      <div class="form-group">
    <li class="list-group-item">{{ informacaoCliente.senha }}</li>
  </div>
</div>
    <label for="itemNome">Confirmação:</label>
    <div>
      <div class="form-group">
    <li class="list-group-item">{{ informacaoCliente.senhaConfirmacao}}</li>
  </div>
</div>    <label for="itemNome">Data de Nascimento:</label>
<div>
      <div class="form-group">
    <li class="list-group-item">{{ informacaoCliente.dataDeNascimento }}</li>
  </div>
</div>    <label for="itemNome">Endereço:</label>
<div>
      <div class="form-group">
    <li class="list-group-item">{{ informacaoCliente.endereco }}</li>
  </div>
</div>
    <label for="itemNome">Cidade:</label>
    <div>
      <div class="form-group">
    <li class="list-group-item">{{informacaoCliente.cidade}}</li>
  </div>
</div>
 
  <label for="itemNome">Estado:</label>
    <div class="form-group">
      <div>
        <li class="list-group-item">{{estadoSelecionado}}</li>
    </div>
</div>
    
    <label for="itemNome">Hobbies:</label>
    <div>
      <div class="form-group">
    <li class="list-group-item">{{ informacaoCliente.hobbies }}</li>
  </div>
</div>    <label for="itemNome">Linguagens de Programação:</label>
<div>
      <div class="form-group">
    <li class="list-group-item">{{ informacaoCliente.liguagensDeProgramacao }}</li>
  </div>
</div>    <label for="itemNome">Biografia:</label>
<div>
      <div class="form-group">
    <li class="list-group-item">{{ informacaoCliente.biografia }}</li>
  </div>
</div>  </ul>
</div>
      </div>
    </div>
</template>

<style scoped>

</style>
