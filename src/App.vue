<script setup>
import { ref } from 'vue'
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
  <main class="container">
    <div class="login-box">
      <h2>Formulário</h2>
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
        <p>Linguagem de programação: {{ usuario.lingProg }}</p>
      </div>
      <form v-else @submit.prevent="confirma">
        <div class="user-box">
          <label>Nome</label>
          <input type="text" v-model="usuario.nome" required="" />
        </div>

        <div class="user-box">
          <label>Email</label>
          <input type="email" v-model="usuario.email" required="">
        </div>

        <div class="user-box">
          <label>Senha </label>
          <input type="password" v-model="usuario.senha" required="" />
        </div>

        <div class="user-box">
          <label>Confirma senha</label>
          <input type="password" v-model="usuario.confirmaSenha" />
        </div>

        <div class="user-box">
          <label>Data de nascimento</label>
          <input type="date" v-model="usuario.dataNasci">
        </div>

        <div class="user-box">
          <label>Endereço</label>
          <input type="endereco" v-model="usuario.endereco" />
        </div>

        <div class="user-box">
          <label>Cidade</label>
          <input type="text" v-model="usuario.cidade" />
        </div>

        <div class="user-box">
          <label>Estado </label>

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
        </div>

        <div class="user-box">
          <label>Hobbies </label>
          <input type="text" v-model="usuario.hobbies" />
        </div>


        <div class="user-box">
          <label>Linguagem De Programacao </label>
          <input type="text" v-model="usuario.lingProg" />
        </div>


        <div class="user-box">
          <label>Biografia</label>
          <input type="text" v-model="usuario.biografia" />
        </div>
      </form>

      
      
      <div class="button">
        <button class="btn" @click="confirma">Enviar</button>
      </div>

    </div>
  </main>
</template>


<style scoped>
main.container {
  position: absolute;
  top: 10%;
  left: 35%;
  bottom: 10%;
  width: 500px;
  box-sizing: border-box;
  box-shadow: 0 15px 25px rgba(0, 0, 0, .6);
  right: auto;
  padding: 2rem;
  border-radius: 8px;
  font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
  background: linear-gradient(#141e30, #4d2158);

}
main h2 {
  margin: 20px;
  padding: 0;
  color: rgb(228, 203, 233);;
  text-align: center;
}
.login-box .user-box input {
  width: 100%;
  font-size: 16px;
  color: #fff;
  border: none;
  border-bottom: 1px solid #fff;
  outline: none;
  background: transparent;
}
.user-box {
  background-color: transparent;
  position: relative;
  margin-bottom: 1.1rem;
}
.login-box form {
  position: relative;
  color: #e2e1e1;
}
.btn {
  margin-top: 2rem;
  padding: 0.4rem;
  width: 100%;
  background-color:rgb(228, 203, 233);
  cursor: pointer;
  color: black;
  font-size: 0.9rem;
  font-weight: 300;
  border-radius: 4px;
  transition: all 0.3s ease;
  border: none;
}

select {
  background-color:rgb(228, 203, 233);;
  margin-top: 10px;
  border-radius: 5px;
  padding-left: 10px;
  margin-left: 10px;
  width: auto;
  border: none;
}
.info {
  color: #f8e2e2;
}</style>