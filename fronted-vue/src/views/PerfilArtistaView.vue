<template>
  <ProtectedNavbar />
  <div class="content">
    <div class="header">
      <div id="inicio">
        <h1>Perfil</h1>
      </div>

      <div id="capa-padre">
        <h1>Artista</h1>
        <hr />
      </div>
    </div>
  </div>
</template>

<script>
import ProtectedNavbar from "../components/ProtectedNavbar.vue";

export default {
  name: 'perfil artista',
  components: {
    ProtectedNavbar,
  },
};
</script>

<style scoped>
#inicio {
  display: flex;
  justify-content: center;
  align-items: center;
  background-image: url("/public/img/fondo.png");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  color: white;
  text-align: center;
  padding: 5px;
  border-radius: 20px;
}

/* Estilos del contenedor principal */
#capa-padre {
  background-color: aliceblue;
  border-radius: 20px;
  text-align: center;
  margin: 5px auto;
  padding: 20px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.25);
  font-size: 16px;
  color: black;
  width: 80%;
  max-width: 550px;
  height: auto;
  position: relative;
  top: 50px;
  max-height: 1000px;
}
/* Estilos del contenedor del formulario */
#app {
  text-align: center;
  margin: 5px;
}
</style>
