<script setup>
import { ref, computed} from 'vue'
const usuario = ref({
  nome: '',
  email: '',
  senha: '',
  confirmaSenha: '',
  dataNasci: 0,
  endereco: '',
  cidade: '',
  estado: '',
  hobbies: '',
  lingProg: '',
  biografia: '',
})

const enviar = ref(false)

function confirma() {
  if (usuario.value.senha != usuario.value.confirmaSenha) {
    alert("senha incorreta")
  }
  else {
    enviar.value = !enviar.value
  }
}

</script>
<template>
  <div>

    <form @submit.prevent="confirma">

      <p>Nome</p>
      <input type="text" v-model="usuario.nome">

      <p>Email</p>
      <input type="email" v-model="usuario.email" />

      <p>Senha </p>
      <input type="password" v-model="usuario.senha" />

      <p>Confirma senha</p>
      <input type="password" v-model="usuario.confirmaSenha" placeholder="confirme sua senha"/>


      <p>Data de nascimento</p>
      <input type="date" v-model="usuario.dataNasci" />

      <p>Endereço</p>
      <input type="endereco" v-model="usuario.endereco" />

      <p>Cidade</p>
      <input type="text" v-model="usuario.cidade" />

      <p>Estado </p>


      <select name="estado" id="estado">
        <option value="AC">Acre</option>enviar
        <option value="AL">Alagoas</option>
        <option value="AP">Amapa</option>
        <option value="AM">Amazonas</option>
        <option value="BA">Bahia</option>
        <option value="CE">Ceara</option>
        <option value="DF">Distrito Federal</option>
        <option value="ES">Espirito Santo</option>
        <option value="GO">Goias</option>
        <option value="MA">Maranhao</option>
        <option value="MT">Mato grosso</option>
        <option value="MS">Mato Grosso do Sul</option>
        <option value="MG">Minas Gerais</option>
        <option value="PA">Pará</option>
        <option value="PB">Paraiba</option>
        <option value="PR">Parana</option>
        <option value="PE">Pernambuco</option>
        <option value="PI">Piaui</option>
        <option value="RJ">Rio de Janeiro</option>
        <option value="RN">Rio Grande do Norte</option>
        <option value="RS">Rio Grande do Sul</option>
        <option value="RO">Rondonia</option>
        <option value="RR">Roraima</option>
        <option value="SC">Santa Catarina</option>
        <option value="SP">São Paulo</option>
        <option value="SE">Sergipe</option>
        <option value="TO">Tocantins</option>
      </select>

      <p>Hobbies </p>
      <input type="text" v-model="usuario.hobbies" />

      <p>linguagem De Programacao </p>
      <input type="text" v-model="usuario.lingProg" />

      <p>biografia</p>
      <input type="text" v-model="usuario.biografia" />
    </form>
    <button @click="confirma">Enviar</button>
    <div class="info" v-if="enviar">
      <p>Suas informações: </p>
      <p>Nome digitado: {{ usuario.nome }}</p>
      <p>Email digitado: {{ usuario.email }}</p>

      <p>Senha digitada: {{ usuario.senha }}</p>


      <p>Data de Nascimento digitada: {{ usuario.dataNasci }}</p>


      <p>Endereco digitado: {{ usuario.endereco }}</p>

      <p>Cidade digitada: {{ usuario.cidade }}</p>


      <p>Estado digitado: {{ usuario.estado }}</p>

      <p>Hobbies digitado: {{ usuario.hobbies }}</p>

      <p>Linguagem de programação  {{ usuario.lingProg }}</p>

    </div>
  </div>
</template>
<style scoped></style>