<template>
  <footer>
    <span> {{ escuela }} </span>
    <span> {{ materia }} </span>
    <span> {{ carrera }} </span>
    <span> {{ alumno }} </span>
    <span> {{ grupo }} </span>
  </footer>
</template>

<script>
export default {
  name: "Datos",
  data() {
    return {
      escuela: "Universidad Tecnológica de Tehuacán",
      materia: "Aplicaciones Web Orientadas a Servicios",
      carrera: "TI Área Desarrollo de Software Multiplataforma",
      alumno: "Alan Castañeda Garcia",
      grupo: "4° A",
    };
  },
};
</script>

<style scoped>
footer{
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: rgb(255, 0, 191);
    color: black;
    padding: 10px 0;
    font-weight: bold;
}
</style>