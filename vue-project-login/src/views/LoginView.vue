<template>
  <div id="app">
    <form class="form" @submit.prevent="login">
      <label for="">Login</label>
      <div class="mb-3">
  <label for="formGroupExampleInput" class="form-label">Nome</label>
  <input v-model="username" type="text" class="form-control" id="username" placeholder="Digite seu Nome">
</div>
<div class="mb-3">
  <label for="formGroupExampleInput2" class="form-label">Digite Sua Senha</label>
  <input v-model="password" type="password" class="form-control" id="password" placeholder="Digite Sua Senha">
</div>
      <button id="btnLogin" type="submit" class="btn btn-success">Success</button>
    </form>
    <div v-if="errorMessage" class="error">{{ errorMessage }}</div>
    <div v-if="loggedIn" class="success">Login successful. Welcome, {{ user.username }}!</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
      errorMessage: '',
      loggedIn: false,
      user: null
    };
  },
  methods: {
    login() {
      // Simulando uma chamada de API para o backend
      fetch('http://localhost:3001/login', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          username: this.username,
          password: this.password
        }),
      })
      .then(response => response.json())
      .then(data => {
        if (data.success) {
          this.loggedIn = true;
          this.user = data.user;
        } else {
          this.errorMessage = data.message;
        }
      })
      .catch(error => {
        console.error('Error:', error);
      });
    }
  }
};
</script>

<style>


.form > label{
  font-size: 3rem;
  border-bottom: 1px solid black;
}

.form {
  display: flex;
  flex-direction:column;
  align-items: center;
  justify-content: center;
}

.form input{
  width: 40vw; height: 6vh;
}

#btnLogin{
  width: 25vw;
}

.error {
  color: red;
  margin-top: 10px;
}

.success {
  color: green;
  margin-top: 10px;
}
</style>
