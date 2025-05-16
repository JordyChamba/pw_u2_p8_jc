<template>
  <div class="container">
    <label for="id_nombre">Nombre: </label>
    <input v-model="nuevoNombre" id="id_nombre" type="text" />

    <label for="id_apellido">Apellido: </label>
    <input v-model="nuevoApellido" id="id_apellido" type="text" />

    <label for="id_edad">Edad: </label>
    <input v-model="nuevaEdad" id="id_edad" type="number" />

    <label for="id_carrera">Carrera: </label>
    <input v-model="nuevaCarrera" id="id_carrera" type="text" />

    <label for="id_ciudad">Ciudad: </label>
    <input v-model="nuevaCiudad" id="id_ciudad" type="text" />

    <button v-on:click="agregarEstudiante">Agregar Estudiante</button>

    <ul>
      <li
        v-for="{ nombre, apellido, edad, carrera, ciudad } in lista"
        :key="nombre + apellido"
      >
        Nombre: {{ nombre }} - Apellido: {{ apellido }} - Edad: {{ edad }} -
        Carrera: {{ carrera }} - Ciudad: {{ ciudad }}
      </li>
    </ul>
  </div>
</template>

<!--- 
 - v-for: iteracion 
 - comunicar datos de entrada con una propiedad ractiva
 - MVC(patron de diseño) Vista: parte visual, 
   Modelo: vista controlador, Controlador: controla todo lo que pasa en la vista

 -->

<script>
export default {
  data() {
    return {
      nuevoNombre: "",
      nuevoApellido: "",
      nuevaEdad: null,
      nuevaCarrera: "",
      nuevaCiudad: "",
      lista: [
        {
          nombre: "Jordy",
          apellido: "Chamba",
          edad: 22,
          carrera: "Sistemas",
          ciudad: "Quito",
        },
        {
          nombre: "Kevin",
          apellido: "Teran",
          edad: 23,
          carrera: "Electrónica",
          ciudad: "Guayaquil",
        },
        {
          nombre: "Jose",
          apellido: "Castillo",
          edad: 21,
          carrera: "Contabilidad",
          ciudad: "Cuenca",
        },
        {
          nombre: "Ana",
          apellido: "Pozo",
          edad: 20,
          carrera: "Derecho",
          ciudad: "Loja",
        },
        {
          nombre: "Erik",
          apellido: "Parra",
          edad: 22,
          carrera: "Medicina",
          ciudad: "Ambato",
        },
        {
          nombre: "Pedro",
          apellido: "Loya",
          edad: 24,
          carrera: "Mecánica",
          ciudad: "Riobamba",
        },
        {
          nombre: "Juan",
          apellido: "Andrade",
          edad: 25,
          carrera: "Arquitectura",
          ciudad: "Ibarra",
        },
      ],
    };
  },
  methods: {
    agregarEstudiante() {
      const nuevo = {
        nombre: this.nuevoNombre,
        apellido: this.nuevoApellido,
        edad: this.nuevaEdad,
        carrera: this.nuevaCarrera,
        ciudad: this.nuevaCiudad,
      };
      this.lista.push(nuevo);

      // Limpiar campos después de agregar
      this.nuevoNombre = "";
      this.nuevoApellido = "";
      this.nuevaEdad = null;
      this.nuevaCarrera = "";
      this.nuevaCiudad = "";
    },
  },
};
</script>

<style></style>
