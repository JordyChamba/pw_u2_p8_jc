<template>
  <div class="container">
    <label for="id_nombre">Nombre: </label>

    <input v-model="nuevoNombre" id="id_nombre" type="text" />
 
    <label for="id_apellido">Apellido: </label>
    <input v-model="nuevoApellido" id="id_apellido" type="text" />
 
    <label for="id_edad">Edad: </label>
    <input v-model="nuevaEdad" id="id_edad" type="number" />
 
    <label for="id_carrera">Carrera: </label>
    <input v-model="nuevaCarrera" id="id_carrera" type="checkbox" />
 
    <label for="id_ciudad">Ciudad: </label>
    <input v-model="nuevaCiudad" id="id_ciudad" type="number" />
 
    <button v-on:click="agregarEstudiante()">Agregar</button>
 
    <ul>

      <li
        v-for="{
          nombre,
          apellido,
          edad,
          ciudad,
          carrera,
        } in lista"
        :key="nombre"
      >
        Nombre: {{ nombre }} - Apellido: {{ apellido }} - Edad: {{ edad }} -
        Ciudad: {{ ciudad}} - Carrera:
        {{ carrera }}
      </li>
    </ul>
 
    <table>
      <thead>
        <th>Nombre</th>
        <th>Apellido</th>
        <th>Edad</th>
        <th>Ciudad</th>
        <th>Carrera</th>
        <th>Acción</th>
      </thead>
      <tbody>
        <tr
          v-for="{
            nombre,
            apellido,
            edad,
            ciudad,
            carrera,
          } in lista"
          :key="nombre"
        >
          <td>{{ nombre }}</td>
          <td>{{ apellido }}</td>
          <td>{{ edad }}</td>
          <td>{{ ciudad }}</td>
          <td>{{ carrera }}</td>
          <td><button>Ver</button></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

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
    },
    editarEstudiante(index) {
      const estudiante = this.lista[index];
      this.nuevoNombre = estudiante.nombre;
      this.nuevoApellido = estudiante.apellido;
      this.nuevaEdad = estudiante.edad;
      this.nuevaCarrera = estudiante.carrera;
      this.nuevaCiudad = estudiante.ciudad;

      this.lista.splice(index, 1);
    },
  },
};
</script>

<style scoped>
.container {
  background: #ffffff;
  border: 1px solid green;
  border-radius: 12px;
  max-width: 700px;
  margin: 50px auto;
  padding: 30px;
  font-family: "Courier New", Courier, monospace;
}

label {
  display: block;
  color: aqua;
  text-align: left;
  font-family: "Courier New", Courier, monospace;
}

input {
  background: rgb(143, 227, 240);
  color: #afaeae;
  width: 99%;
  border-radius: 8px;
  margin-bottom: 20px;
  border: 1px solid rgb(26, 131, 26);
  padding: 5px 5px;
}

button {
  border-radius: 8px;
  font-family: "Courier New", Courier, monospace;
  font-size: 15px;
  cursor: pointer;
  padding: 12px 20px;
  border: none;
  width: 100px;
}

button:active {
  background: rgba(27, 100, 78, 0.651);
}

ul {
  list-style-type: none;
  margin-top: 40px;
}

li {
  margin-bottom: 20px;
  padding: 15px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #cbe6db;
}

table {
  width: 100%;
  border-collapse: separate;
  border-spacing: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-size: 0.95rem;
  background-color: #fff;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.05);
  border-radius: 8px;
  overflow: hidden;
}

thead {
  background-color: #f4f6f8;
}

thead th {
  text-align: left;
  padding: 15px;
  color: #333;
  font-weight: 600;
  border-bottom: 2px solid #e3e6ea;
}

tbody tr {
  transition: background-color 0.2s;
}

tbody tr:nth-child(even) {
  background-color: #f9fafb;
}

tbody tr:hover {
  background-color: #eef3f9;
}

tbody td {
  padding: 15px;
  border-bottom: 1px solid #e3e6ea;
  color: #444;
}
</style>
