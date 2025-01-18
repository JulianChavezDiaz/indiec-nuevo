<template>
  <ProtectedNavbar />
  <div :class="['content', theme]">
    <!-- Contenedor principal -->
    <div id="inicio" :class="theme">
      <h1>Inicio</h1> <!-- Palabra clave: Inicio -->
    </div>
    <div id="app-2"></div>
    <!-- Botón para alternar el tema -->
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
    // Variable que controla el tema
    const theme = ref(localStorage.getItem("theme") || "light");

    // Método para alternar entre claro y oscuro
    const toggleTheme = () => {
      theme.value = theme.value === "light" ? "dark" : "light";
      localStorage.setItem("theme", theme.value); // Guardar en localStorage
    };

    return { theme, toggleTheme };
  },
  methods: {
    // Método para cerrar sesión
    logout() {
      localStorage.removeItem("token");
      this.$router.push("/login");
    },
  },
};
</script>

<style scoped>
/* Base del contenedor principal */
.content {
  min-height: 100vh;
  transition: background-color 0.3s ease, color 0.3s ease; /* Transición suave */
  display: flex;
  flex-direction: column; /* Organización en columna */
}

/* Estilo para el tema claro */
.light {
  background-color: #ffffff; /* Fondo blanco */
  color: #000000; /* Texto negro */
}

/* Estilo para el tema oscuro */
.dark {
  background-color: #121212; /* Fondo oscuro */
  color: #e0e0e0; /* Texto claro */
}

/* Botón para cambiar tema */
.theme-toggle {
  margin: 20px auto;
  padding: 10px 20px;
  border: none;
  border-radius: 8px;
  background-color: #4caf50; /* Verde */
  color: #ffffff;
  cursor: pointer;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.theme-toggle:hover {
  background-color: #45a049; /* Verde oscuro al pasar el mouse */
}

/* Contenedor del encabezado */
#inicio {
  display: flex;
  justify-content: center;
  align-items: center;
  background-image: url("/public/img/fondo.png"); /* Imagen de fondo */
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  text-align: center;
  padding: 20px;
  border-radius: 20px;
  margin-top: 10px;
  width: 100%;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}

/* Estilo para el texto dentro de #inicio en temas claros */
#inicio.light h1 {
  color: #000000; /* Negro para tema claro */
}

/* Estilo para el texto dentro de #inicio en temas oscuros */
#inicio.dark h1 {
  color: #e0e0e0; /* Blanco o gris claro para tema oscuro */
}

/* Ajuste para el segundo contenedor */
#app-2 {
  text-align: center;
  flex: 1; /* Expande el contenido */
}

/* Otros estilos */
.contenedor {
  height: 40vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
