<template>
  <div class="login-wrapper">
    <div class="login-container">
      <h2>Entrar na Conta</h2>
      <form @submit.prevent="handleLogin">
        <div class="input-group">
          <label for="email">E-mail</label>
          <input type="email" id="email" v-model="email" required placeholder="seuemail@exemplo.com" @focus="limparErro" />
        </div>

        <div class="input-group">
          <label for="senha">Senha</label>
          <input type="password" id="senha" v-model="senha" required placeholder="Digite sua senha" @focus="limparErro" />
        </div>
        <p v-if="erro" class="erro-msg">{{ erro }}</p>
        <button class="login-btn" type="submit">Login</button>
      </form>

      <div class="footer">
        <p>Não tem uma conta? <a href="#">Cadastre-se</a></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      email: '',
      senha: '',
      erro:''
    }
  },
  methods: {
  handleLogin() {
    this.erro = ''; // limpa erros anteriores

    if (!this.validateEmail(this.email)) {
      this.erro = 'Por favor, insira um e-mail válido.';
      return;
    }

    if (this.senha.length < 6) {
      this.erro = 'A senha deve ter pelo menos 6 caracteres.';
      return;
    }

    // lógica de login
    console.log('Email:', this.email);
    console.log('Senha:', this.senha);
  },
  validateEmail(email) {
    const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return regex.test(email);
  },
  limparErro() {
    this.erro = '';
  }
}
}
</script>

<style>
* {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
  }

    #routerMain {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
  min-height: calc(100vh - 100px); /* Ajuste baseado no header/footer */
  }
 
  .login-container {
    background-color: white;
    padding: 40px 30px;
    border-radius: 16px;
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
    width: 100%;
    max-width: 400px;
    animation: fadeIn 1s ease;
  }

    .login-container h2 {
      text-align: center;
      margin-bottom: 24px;
      color: #333;
    }

    .input-group {
      margin-bottom: 20px;
    }

    .input-group label {
      display: block;
      font-size: 14px;
      color: #555;
      margin-bottom: 6px;
    }

    .input-group input {
      width: 100%;
      padding: 12px;
      border-radius: 8px;
      border: 1px solid #ccc;
      transition: border 0.3s;
    }

    .input-group input:focus {
      border-color: #667eea;
      outline: none;
    }

    .login-btn {
      width: 100%;
      padding: 12px;
      background-color: #667eea;
      color: white;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    .login-btn:hover {
      background-color: #5a67d8;
    }

    .erro-msg {
      color: #e53e3e;
      background-color: #fed7d7;
      padding: 10px;
      border-radius: 8px;
      margin-bottom: 16px;
      font-size: 14px;
      text-align: center;
    }

    .footer {
      margin-top: 16px;
      text-align: center;
      font-size: 14px;
      color: #777;
    }

    .footer a {
      color: #667eea;
      text-decoration: none;
    }
 
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(-20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @media (max-width: 500px) {
      .login-container {
        padding: 30px 20px;
      }
    }
</style>