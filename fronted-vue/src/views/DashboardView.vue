<template>
  <ProtectedNavbar />
  <div class="content">
    <div class="header">
      <div id="inicio">
        <h1>Inicio</h1>
      </div>
    </div>
    <div id="app-2">
    </div>
  </div>
</template>

<script>
import ProtectedNavbar from "../components/ProtectedNavbar.vue";

export default {
  name: "Dashboard",
  components: {
    ProtectedNavbar,
  },
  methods: {
    logout() {
      localStorage.removeItem("token");
      this.$router.push("/login");
    },
  },
};
</script>


<style scoped>
/*estilos del dasboard*/
@import "../../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../../node_modules//@syncfusion//ej2-buttons/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-vue-calendars/styles/material.css";

/*Estilos Calendar*/
.contenedor {
  height: 40vh;

  display: flex;
  justify-content: center;
  align-items: center;
}

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
  /* Centra el texto dentro del div */
  padding: 5px;
  border-radius: 20px;

}

#capa-padre {
  background-color: aliceblue;
  border-radius: 20px;
  text-align: center;
  margin: 5px auto;
  padding: 10px;
  box-shadow: 5px 2px 3px 1px rgba(0, 0, 0, 0.164);
  font-size: 16px;
  color: black;
}

#app-2 {
  text-align: center;
}


</style>