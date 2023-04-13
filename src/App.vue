<script setup>
import { ref, computed } from 'vue'
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

      <form @submit.prevent="confirma">

        <div class="user-box">
          <p>Nome</p>
          <input type="text" v-model="usuario.nome" required="" />
        </div>

        <div class="user-box">
          <p>Email</p>
          <input type="email" v-model="usuario.email" required="">
        </div>

        <div class="user-box">
          <p>Senha </p>
          <input type="password" v-model="usuario.senha" required="" />
        </div>


        <div class="user-box">
          <p>Confirma senha</p>
          <input type="password" v-model="usuario.confirmaSenha" placeholder="confirme sua senha" required="" />
        </div>


        <div class="user-box">
          <p>Data de nascimento</p>
          <input type="date" v-model="usuario.dataNasci" required="">
        </div>


        <div class="user-box">
          <p>Endereço</p>
          <input type="endereco" v-model="usuario.endereco" required="" />
        </div>

        <div class="user-box">
          <p>Cidade</p>
          <input type="text" v-model="usuario.cidade" />
        </div>


        <div class="user-box">
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
        </div>

        <div class="user-box">
          <p>Hobbies </p>
          <input type="text" v-model="usuario.hobbies" />
        </div>


        <div class="user-box">
          <p>Linguagem De Programacao </p>
          <input type="text" v-model="usuario.lingProg" />
        </div>


        <div class="user-box">
          <p>Biografia</p>
          <input type="text" v-model="usuario.biografia" />
        </div>
      </form>

      <div class="button">
        <button @click="confirma">Enviar</button>
      </div>


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

        <p>Linguagem de programação {{ usuario.lingProg }}</p>

      </div>
    </div>
  </main>
</template>
<style scoped>
main.container {
  position: absolute;
  top: 10%;
  left: 30%;
  margin-bottom: auto;
  width: 600px;


  background: rgba(0, 0, 0, .5);
  box-sizing: border-box;
  box-shadow: 0 15px 25px rgba(0, 0, 0, .6);
  border-radius: 10px;
right:auto;
  padding: 2rem;

  border-radius: 8px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;


  background: linear-gradient(#141e30, #95b0cc);

}

main h2 {
  margin:  20px;
  padding: 0;
  color: #fff;
  text-align: center;
  
}



.login-box .user-box input {
  width: 100%;
 
  font-size: 16px;
  color: #fff;
  margin-bottom: 30px;
  border: none;
  border-bottom: 1px solid #fff;
  outline: none;
  background: transparent;
}


.login-box form {
  position: relative;
  
  color: #ffffff;
 
 

  
}
.button {
  
  align-items: center;
  background-image: linear-gradient(144deg,#AF40FF, #5B42F3 50%,#00DDEB);
  border: 0;
  border-radius: 8px;
  box-shadow: rgba(151, 65, 252, 0.2) 0 15px 30px -5px;
  box-sizing: border-box;
  color: #FFFFFF;
  display: flex;
  font-family: Phantomsans, sans-serif;
  font-size: 20px;
  justify-content: center;
  line-height: 1em;
  max-width: 100%;
  min-width: 140px;
  padding: 3px;
  text-decoration: none;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  white-space: nowrap;
  cursor: pointer;
}

.button:active,
.button:hover {
  outline: 0;
}

.button span {
  background-color: rgb(5, 6, 45);
  padding: 16px 24px;
  border-radius: 6px;
  width: 100%;
  height: 100%;
  transition: 300ms;
}

.button:hover span {
  background: none;
}

@media (min-width: 768px) {
  .button-64 {
    font-size: 24px;
    min-width: 196px;
  }
}



</style>