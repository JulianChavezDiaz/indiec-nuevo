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

.chart-container {
  margin-top: 20px;
  display: flex;
  justify-content: space-around;
  /* Alineación de los gráficos */
}

.chart-item {
  width: 50%;
  /* Ajusta el tamaño de cada gráfico */
}

.larger-chart {
  width: 50%;
  /* Ajusta el tamaño del gráfico de líneas para que sea más grande */
}

canvas {
  width: 100% !important;
  /* Asegura que el canvas llene su contenedor */
  height: auto !important;
  /* Asegura que el canvas mantenga la proporción */
}

.table-container {
  margin-top: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #f9f9f9;
  padding: 10px;
  width: 80%;
  /* Ajusta el tamaño de la tabla */
  max-width: 800px;
  /* Ajusta el tamaño máximo de la tabla */
  margin-left: auto;
  margin-right: auto;
  /* Centra horizontalmente */
}

table {
  width: 100%;
  border-collapse: collapse;
}

th,
td {
  padding: 8px;
  text-align: left;
  border-bottom: 1px solid #ddd;
}

th {
  background-color: #f2f2f2;
}
</style>