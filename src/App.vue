<script setup>
import { ref, computed } from 'vue'
const usuario = ref({
  nome: '',
  email: '',
  senha: '',
  dataNasci: 0,
  endereco: '',
  cidade: '',
  estado: '',
  hobbies: '',
  lingProg: '',
  biografia: '',
})

const confirmaUsuario = computed(() => {
  if (usuario.value.nome.length >= 3 && usuario.value.nome.length
    < 20 && usuario.value.email.includes("@gmail.com") && usuario.value.senha === usuario.value.senha &&
    usuario.value.dataNasci > 18 && usuario.value.endereco.length > 3 && usuario.value.endereco.length > 3 &&
    usuario.value.cidade.length > 3 && usuario.value.estado.length > 4 && usuario.value.hobbies.length > 3 &&
    usuario.value.lingProg.length > 3 && usuario.value.biografia.length) {

  }
})
</script>
<template>
  <div>

    <form action="">

      <p>Nome digitado é: {{ usuario.nome }}</p>
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

      <p>linguagem De Programacao digitada é: {{ usuario.linguagemProgramacao }}</p>
      <input type="text" v-model="usuario.linguagemProgramacao" />

      <p>biografia digitado é: {{ usuario.biografia }}</p>
      <input type="text" v-model="usuario.biografia" />
    </form>
    <button type="submit" @click="confirmaUsuario">
   Aparecer
    </button>
  </div>
</template>
<style scoped></style>