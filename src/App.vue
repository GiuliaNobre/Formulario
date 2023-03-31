<script setup>
import { ref } from 'vue'
const usuario = ref({
  nome: '',
  email: '',
  senha: '',
  dataNasci: '',
  endereco: '',
  cidade: '',
  estado: '',
  hobbies: '',
  linguagemProg: '',
  biografia: '',
})

</script>
<template>

<p>Nome digitado é: {{usuario.nome}}</p>
<input type="text" v-model="usuario.nome">

<p>Email digitado é: {{ usuario.email }}</p>
<input type="email" v-model="usuario.email" />

<p>Senha digitada é: {{ usuario.senha }}</p>
<input type="password" v-model="usuario.senha" />

<p>Data de Nascimento digitada é: {{ usuario.dataNasci }}</p>
<input type="number" v-model="usuario.dataNasci" />

<p>Endereco digitado é: {{ usuario.endereco }}</p>
<input type="endereco" v-model="usuario.endereco" />

<p>Cidade digitada é: {{ usuario.cidade }}</p>
<input type="text" v-model="usuario.cidade" />

<p>Estado digitado é: {{ usuario.estado }}</p>
<input type="text" v-model="usuario.estado" />
<select name="estado" id="estado">
  <option value="AC">Acre</option>
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

<p>Hobbies digitados são: {{ usuario.hobbies }}</p>
<input type="text" v-model="usuario.hobbies" />

<p>linguagem De Programacao digitada é: {{ usuario.linguagemProgramacao}}</p>
<input type="text" v-model="usuario.linguagemProgramacao" />

<p>biografia digitado é: {{ usuario.biografia }}</p>
<input type="text" v-model="usuario.biografia" />

</template>
<style scoped>


</style>