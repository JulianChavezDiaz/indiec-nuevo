<template>
  <ProtectedNavbar />
  <div :class="['content', theme]">
    <div id="inicio">
      <h1>Inicio</h1>
    </div>
    <div id="app-2"></div>
    <!-- Botón para cambiar de tema -->
    <button @click="toggleTheme" class="theme-toggle">
      Cambiar Tema
    </button>
  </div>
</template>

<script>
import ProtectedNavbar from "../components/ProtectedNavbar.vue";
import { ref } from "vue";

export default {
  name: "Dashboard",
  components: {
    ProtectedNavbar,
  },
  setup() {
    // Estado inicial del tema
    const theme = ref(localStorage.getItem("theme") || "light");

    // Alternar tema entre claro y oscuro
    const toggleTheme = () => {
      theme.value = theme.value === "light" ? "dark" : "light";
      localStorage.setItem("theme", theme.value); // Guardar preferencia en localStorage
    };

    return { theme, toggleTheme };
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
/* Estilo base */
.content {
  min-height: 100vh;
  transition: background-color 0.3s ease, color 0.3s ease;
  display: flex;
  flex-direction: column; /* Coloca los elementos en una columna */
}

/* Estilo modo claro */
.light {
  background-color: #ffffff;
  color: #000000;
}

/* Estilo modo oscuro */
.dark {
  background-color: #121212;
  color: #e0e0e0;
}

/* Botón para cambiar el tema */
.theme-toggle {
  margin: 20px auto; /* Centra horizontalmente */
  padding: 10px 20px;
  border: none;
  border-radius: 8px;
  background-color: #4caf50; /* Botón verde */
  color: #ffffff;
  cursor: pointer;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.theme-toggle:hover {
  background-color: #45a049; /* Verde más oscuro al pasar el cursor */
}

/* Estilos del encabezado */
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
  padding: 20px; /* Más espacio para hacerlo visible */
  border-radius: 20px;
  margin-top: 10px; /* Separación desde la parte superior */
  width: 100%; /* Asegura que ocupe todo el ancho */
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}

/* Ajustes del contenedor adicional */
#app-2 {
  text-align: center;
  flex: 1; /* Permite que este contenedor ocupe el espacio restante */
}

/* Estilos adicionales */
.contenedor {
  height: 40vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
