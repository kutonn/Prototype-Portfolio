<template>
  <div class="login-page fade-in">
    <div class="card login-card">
      <h1>Welcome Back</h1>
      <p class="subtitle">Please sign in to continue</p>

      <input
        v-model="username"
        placeholder="Username"
      />

      <input
        v-model="password"
        type="password"
        placeholder="Password"
      />

      <button @click="login">Login</button>

      <p v-if="error" class="error">{{ error }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      username: '',
      password: '',
      error: ''
    }
  },
  methods: {
    login() {
      if (this.username === 'admin' && this.password === '1234') {
        this.$router.push('/portfolio/profile')
      } else {
        this.error = 'Invalid login credentials'
      }
    }
  }
}
</script>

<style scoped>
.login-page {
  min-height: 100vh;
  display: grid;
  place-items: center;
  background: #f9fafb;
}

.login-card {
  width: 100%;
  max-width: 360px;
  text-align: center;
}

.subtitle {
  color: #6b7280;
  margin-bottom: 1.5rem;
  font-size: 0.95rem;
}

.error {
  color: #dc2626;
  margin-top: 1rem;
  font-size: 0.9rem;
}
</style>
