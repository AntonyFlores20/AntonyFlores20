//Register.VUE
<template>
  <div>
    <h2>Registro</h2>
    <form @submit.prevent="register">
      <label>Nombre de usuario:</label>
      <input v-model="username" required />
      <label>Contraseña:</label>
      <input type="password" v-model="password" required />
      <button type="submit">Registrarse</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
    };
  },
  methods: {
    async register() {
      // Llama a tu API para registrar al usuario
      try {
        const response = await this.$axios.post('/api/register', {
          username: this.username,
          password: this.password,
        });
        console.log('Usuario registrado:', response.data);
      } catch (error) {
        console.error('Error al registrar:', error);
      }
    },
  },
};
</script

<!---
AntonyFlores20/AntonyFlores20 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
