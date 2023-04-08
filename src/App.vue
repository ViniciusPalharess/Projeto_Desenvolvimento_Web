<script setup>
import { ref } from 'vue'

const informacaoCliente = ref({
  nome: '',
  email: '',
  senha: '',
  senhaConfirmacao: '',
  confirma: '',
  data: 0,
  endereco: '',
  cidade: '',
  estado: '',
  biografia: ''
});

function enviarFormulario() {
  informacoesEnviadas.value = {
    nome: informacaoCliente.value.nome,
    email: informacaoCliente.value.email,
    senha: informacaoCliente.value.senha,
    senhaConfirmacao: informacaoCliente.value.senhaConfirmacao,
    dataDeNascimento: informacaoCliente.value.dataDeNascimento,
    endereco: informacaoCliente.value.endereco,
    cidade: informacaoCliente.value.cidade,
    estado: estadoSelecionado.value,
    hobbies: hobbies.value,
    linguagens: linguagens.value,
    biografia: informacaoCliente.value.biografia
  }
};

const hobbies = ref('');
const linguagens = ref('');
const estadoSelecionado = ref('');
const mostrarSenha = ref(false);
const mostrarSenhaConfirmacao = ref(false);
const informacoesEnviadas = ref(null);

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
    <form @submit.prevent="enviarFormulario">
      <div class="card text-bg-secondary mb-5 mt-5">
        <div class="card-header text-bg-dark text-center">
          <h1>Formulário</h1>
        </div>
        <div class="card-body">
          <h2 class="card-title">Insira os dados:</h2>

          <div class="form-group">
            <label for="informacaoCliente.nome">Nome:</label>
            <input
              type="text"
              v-model="informacaoCliente.nome"
              class="form-control"
              placeholder="Nome"
              required
            />
          </div>

          <div class="form-group">
            <label for="informacaoCliente.email">E-mail:</label>
            <input
              type="email"
              v-model="informacaoCliente.email"
              class="form-control"
              placeholder="E-mail"
              required
            />
          </div>

          <div class="form-group">
            <label for="informacaoCliente.senha" class="form-label">Senha</label>
            <div class="input-group">
              <input
                class="form-control"
                v-model="informacaoCliente.senha"
                :type="mostrarSenha ? 'text' : 'password'"
              />
              <button
                class="btn btn-dark"
                type="button"
                @click="mostrarSenha = !mostrarSenha"
              >
                Mostrar
              </button>
            </div>
          </div>

          <div class="form-group">
            <label for="senhaConfirmacao" class="form-label">Confirme sua senha</label>
            <div class="input-group">
              <input
                class="form-control"
                v-model="informacaoCliente.senhaConfirmacao"
                :type="mostrarSenhaConfirmacao ? 'text' : 'password'"
              />
              <button
                class="btn btn-dark"
                type="button"
                @click="mostrarSenhaConfirmacao = !mostrarSenhaConfirmacao"
              >
                Mostrar
              </button>
            </div>
          </div>

          <div class="form-group">
            <label for="informacaoCliente.dataDeNascimento">Data de Nascimento:</label>
            <input
              type="date"
              v-model="informacaoCliente.dataDeNascimento"
              class="form-control"
              placeholder="Data de Nascimento"
              required
            />
          </div>
          
          <div>
            <div class="form-group">
              <label for="estadoSelecionado">Estado:</label>
              <select v-model="estadoSelecionado" class="form-control" required>
                
                <option value="" disabled>Selecione o estado</option>
                <option v-for="estado in estados" :key="estado.sigla" :value="estado.nomeEstado">
                  {{ estado.sigla }} - {{ estado.nomeEstado }}
                </option>
              </select>
            </div>


          <div class="form-group">
            <label for="informacaoCliente.cidade">Cidade:</label>
            <input
              type="text"
              v-model="informacaoCliente.cidade"
              class="form-control"
              placeholder="Cidade"
              required
            />
          </div>

          <div class="form-group">
            <label for="informacaoCliente.endereco">Endereço:</label>
            <input
              type="text"
              v-model="informacaoCliente.endereco"
              name="endereco"
              class="form-control"
              placeholder="Endereço"
              required
            />
          </div>

            <div class="form-group">
              <label for="hobbies">Hobbies:</label>
              <input
                type="text"
                v-model="hobbies"
                name="Hobbies"
                class="form-control"
                placeholder="Hobbies"
                required
              />
            </div>
            <div class="form-group">
              <label for="linguagens">Linguagens de Programação:</label>
              <input
                type="text"
                v-model="linguagens"
                name="Linguagens de Programacao"
                class="form-control"
                placeholder="Linguagens de Programação"
                required
              />
            </div>
            <div class="form-group">
              <label for="informacaoCliente.biografia">Biografia:</label>
              <input
                type="text"
                v-model="informacaoCliente.biografia"
                name="Biografia"
                class="form-control"
                placeholder="Biografia"
                required
              />
            </div>
            <div class="d-grid gap-2 mt-3">
              <button class="btn btn-primary" type="submit" @click="enviarFormulario">
                Enviar
              </button>
            </div>
          </div>
        </div>
      </div>
    </form>
  </div>

  <div v-if="informacoesEnviadas">
    <div class="card text-bg-secondary ms-4 mb-5 mt-5 ">
      <div class="card-header text-bg-dark text-center">
        <h1>Formulário</h1>
      </div>
      <div class="card-body">
        <h2 class="card-title">Seus dados:</h2>
        <div>
          <ul class="list-group list-group-flush">
            <label for="itemNome">Nome:</label>
            <div>
              <div class="form-group">
                <li class="list-group-item" >{{ informacoesEnviadas.nome }}</li>
              </div>
            </div>

            <label for="itemNome">Email:</label>
            <div>
              <div class="form-group">
                <li class="list-group-item">{{ informacoesEnviadas.email }}</li>
              </div>
            </div>

            <label for="itemNome">Senha:</label>
            <div>
              <div class="form-group">
                <li class="list-group-item">{{ informacoesEnviadas.senha }}</li>
              </div>
            </div>
            <label for="itemNome">Confirmação:</label>
            <div>
              <div class="form-group">
                <li class="list-group-item">{{ informacoesEnviadas.senhaConfirmacao }}</li>
              </div>
            </div>
            <label for="itemNome">Data de Nascimento:</label>
            <div>
              <div class="form-group">
                <li class="list-group-item">{{ informacoesEnviadas.dataDeNascimento }}</li>
              </div>
            </div>

            <label for="itemNome">Estado:</label>
            <div class="form-group">
              <div>
                <li class="list-group-item">{{ informacoesEnviadas.estado }}</li>
              </div>
            </div>

            <label for="itemNome">Cidade:</label>
            <div>
              <div class="form-group">
                <li class="list-group-item">{{ informacoesEnviadas.cidade }}</li>
              </div>
            </div>

            <label for="itemNome">Endereço:</label>
            <div>
              <div class="form-group">
                <li class="list-group-item">{{ informacoesEnviadas.endereco }}</li>
              </div>
            </div>

            <label for="itemNome">Hobbies:</label>
            <div>
              <div class="form-group">
                <li class="list-group-item">{{ informacoesEnviadas.hobbies }}</li>
              </div>
            </div>
            <label for="itemNome">Linguagens de Programação:</label>
            <div>
              <div class="form-group">
                <li class="list-group-item">{{ informacoesEnviadas.linguagens }}</li>
              </div>
            </div>
            <label for="itemNome">Biografia:</label>
            <div>
              <div class="form-group">
                <li class="list-group-item">{{ informacoesEnviadas.biografia }}</li>
              </div>
            </div>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>


</style>
