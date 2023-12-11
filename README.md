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
  template>
  <div>
    <h2>Iniciar Sesión</h2>
    <form @submit.prevent="login">
      <label>Nombre de usuario:</label>
      <input v-model="username" required />
      <label>Contraseña:</label>
      <input type="password" v-model="password" required />
      <button type="submit">Iniciar Sesión</button>
    </form>
  </div>
</template>
//Login.VUE
<script>
export default {
  data() {
    return {
      username: '',
      password: '',
    };
  },
  methods: {
    async login() {
      // Llama a tu API para autenticar al usuario
      try {
        const response = await this.$axios.post('/api/login', {
          username: this.username,
          password: this.password,
        });
        console.log('Usuario autenticado:', response.data);
      } catch (error) {
        console.error('Error al autenticar:', error);
      }
    },
  },
};
</script>
//Lista.VUE
<!-- components/Listado.vue -->
<template>
  <div>
    <h2>Listado</h2>
    <ul>
      <li v-for="item in items" :key="item.id">{{ item.nombre }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [],
    };
  },
  mounted() {
    // Llama a tu API para obtener el listado de elementos
    this.fetchItems();
  },
  methods: {
    async fetchItems() {
      try {
        const response = await this.$axios.get('/api/items');
        this.items = response.data;
      } catch (error) {
        console.error('Error al obtener el listado:', error);
      }
    },
  },
};
</script>

<!---
AntonyFlores20/AntonyFlores20 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
