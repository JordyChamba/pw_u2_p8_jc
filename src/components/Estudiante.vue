<template>
  <div class="container">
    <label for="id_nombre">Nombre: </label>
    <input v-model="nuevoNombre" id="id_nombre" type="text" />
    <label for="id_apellido">Apellido: </label>
    <input v-model="nuevoApellido" id="id_apellido" type="text" />
    <!--- Elemento de entrada -->
    <button v-on:click="agregarEstudiante">Agregar Estudiante</button>
    {{ nuevoNombre}}<!--- Se vinculo, los dos se emparejan -->
    <ul>
      <li v-for="{ nombre, apellido } in lista" :Key="nombre">
        Nombre: {{ nombre }} - Apellido: {{ apellido }}
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
      nuevoNombre: "nuevo",
      nuevoApellido: "nuevo",
      lista: [
        { nombre: "Jordy", apellido: "Chamba" },
        { nombre: "Kevin", apellido: "Teran" },
        { nombre: "Jose", apellido: "Castillo" },
        { nombre: "Ana", apellido: "Pozo" },
        { nombre: "Erik", apellido: "Parra" },
        { nombre: "Pedro", apellido: "Loya" },
        { nombre: "Juan", apellido: "Andrade" },
      ],
    };
  },
  methods:{
    agregarEstudiante(){
        const nuevo= {
            nombre: this.nuevoNombre,
            apellido: this.nuevoApellido ,
        };
        /*this.lista.unshift(nuevo);*/
        this.lista.push(nuevo);
    },
  },
};
</script>

<style></style>
