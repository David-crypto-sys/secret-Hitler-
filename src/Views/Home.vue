<template>
    <div class="home">
      <h1>Secret Hitler</h1>
      <div class="botones">
        <button
          v-for="btn in botones"
          :key="btn.texto"
          @click="btn.accion"
          class="boton"
        >
          {{ btn.texto }}
        </button>
      </div>
    </div>
  </template>
  
  <script setup>
  import { useRouter } from "vue-router";

  const router = useRouter();
  
  function crearPartida() {
    console.log("Crear partida");
    router.push("/create-game")
  }
  
  function unirseAPartida() {
    console.log("Unirse a partida");
    router.push("/join-game")
  }
  
  const botones = [
    { texto: "Crear partida", accion: crearPartida },
    { texto: "Unirse", accion: unirseAPartida },
  ];
  </script>
  
  <style scoped>
.home {
  color: #1b1b1b;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.botones {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.boton {
  background-color: #1b1b1b;
  color: white;
  border: none;
  padding: 1rem 2rem;
  margin: 1rem;
  border-radius: 10px;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.2s ease;
  width: 200px; /* mismo ancho para ambos botones */
  text-align: center;
}

.boton:hover {
  background-color: white;
  color: black;
}
</style>

  