<template>
  <ProtectedNavbar />
  <top-bar />
  <div :class="['content', theme]">
    <div class="content-wrapper" :class="theme">
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
  </div>
</template>

<script>
import ProtectedNavbar from "../components/ProtectedNavbar.vue";
import TopBar from "@/components/top-bar.vue";

export default {
  name: "perfil artista",
  components: {
    ProtectedNavbar,
    TopBar

  },
};
</script>

<style scoped>
/*com*/
.content-wrapper {
  margin-top: 80px; /* Ajusta este valor según la altura de tu top-bar */
}

#inicio {
  display: flex;
  justify-content: center;
  align-items: center;
  background-image: url("/public/img/fondo 2.png");
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
