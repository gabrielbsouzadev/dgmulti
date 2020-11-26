<template>
    <nav class="navbar navbar-expand-lg navbar-dgmulti">
      <a class="navbar-brand" href="#">DgMulti</a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto" v-if="usuarioestaLogado">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/clientes" class="nav-link">Clientes</router-link>
          </li>
          <li class="nav-item">
            <a href="#" class="nav-link" @click.prevent="efetuarLogout">Logout</a>
          </li>
        </ul>
        <ul class="navbar-nav mr-auto" v-else>
          <li class="nav-item">
            <router-link class="nav-link" to="/login">Login</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/cadastre-se" class="nav-link">Registre-se</router-link>
          </li>
        </ul>
      </div>
    </nav>
</template>

<script>
export default {
  methods: {
    efetuarLogout() {
      localStorage.removeItem("token");
      this.$router.push({ name: "login" });
    }
  },
  computed: {
    usuarioestaLogado () {
      return Boolean(localStorage.getItem('token'))
    }
  }
};
</script>

<style>
.navbar {
  background: #27ae60;
}
.navbar-dgmulti a {
  color: #fff;
}
.navbar-dgmulti a:hover {
  color: #000;
}
</style>