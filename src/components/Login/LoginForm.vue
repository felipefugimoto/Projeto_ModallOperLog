<template>
  <div :class="['mensagem', tipoMensagem]" v-if="mensagem">{{ mensagem }}</div>

  <form id="loginForm" class="loginForm" @submit.prevent="handleLogin">
    <div class="logoMini">
      <img width="120" :src="Logo3" />
    </div>
    <h1 class="header">Faça login para iniciar sua sessãosssssss</h1>

    <div class="input">
      <i class="bi bi-envelope"></i>
      <input id="name" required v-model="email" type="email" placeholder="Email" />
    </div>

    <div class="input">
      <i class="glyphicon glyphicon-lock"></i>
      <input id="pass" required v-model="senha" type="password" placeholder="Senha" />
    </div>

    <div class="checkbox icheck">
      <label>
        <input id="checkbox" v-model="lembrar" name="rememberMe" type="checkbox" />
        <span>Lembrar-me</span>
      </label>
    </div>

    <button class="buttonContainer" type="submit">Entrar</button>
  </form>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import Logo3 from '@/assets/img/logo3.png';
import { useRouter } from 'vue-router'; // se estiver usando vue-router

const email = ref('');
const senha = ref('');
const lembrar = ref(false);

const mensagem = ref('');
const tipoMensagem = ref('');
const router = useRouter(); // para redirecionar

function handleLogin() {
  if (email.value === 'felipe.fugimoto3@gmail.com' && senha.value === '123456') {
    mensagem.value = 'Login realizado com sucesso!';
    tipoMensagem.value = 'sucesso';

    setTimeout(() => {
      mensagem.value = '';
      tipoMensagem.value = '';
      router.push('/index'); // redireciona para próxima página
    }, 3000);
  } else {
    mensagem.value = 'Usuário não cadastrado.';
    tipoMensagem.value = 'erro';

    setTimeout(() => {
      mensagem.value = '';
      
      tipoMensagem.value = '';
    }, 3000);
  }
}
</script>

<style>
.logoMini {
  display: flex;
  justify-content: center;
  margin-bottom: 15px;
}
.header {
  font-size: 20px;
  color: #57585a;
  font-weight: 700;
  text-align: center;
  width: 80%;
  margin: 0 auto 20px;
}
.loginForm .input {
  display: flex;
  width: 100%;
  gap: 10px;
  align-items: center;
  justify-content: center;
  border: 2px solid #ce1728;
  margin-bottom: 15px;
  height: 44px;
  border-radius: 15px;
  font-size: 16px;
  padding: 0 10px;
}
.loginForm .input i {
  font-size: 20px;
  color: #ce1728;
}
.loginForm input {
  outline: none;
  background: none;
  border: none;
  width: 100%;
}
.checkbox {
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
}
.checkbox label {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 15px;
  color: #666666;
  font-weight: 500;
  cursor: pointer;
  user-select: none;
}
.checkbox input[type='checkbox'] {
  width: 18px;
  height: 18px;
  accent-color: #ce1728;
  cursor: pointer;
}
.buttonContainer {
  background: #ce1728;
  border-radius: 15px;
  height: 44px;
  border: none;
  font-weight: bold;
  color: white;
  font-size: 16px;
  width: 100%;
  transition: 0.3s;
  cursor: pointer;
}

/* Mensagem de sucesso e erro */
.mensagem {
  text-align: center;
  margin-bottom: 15px;
  padding: 10px;
  border-radius: 10px;
  font-weight: bold;
  width: 100%;
}
.sucesso {
  background-color: #d4edda;
  color: #155724;
}
.erro {
  background-color: #f8d7da;
  color: #721c24;
}
</style>
