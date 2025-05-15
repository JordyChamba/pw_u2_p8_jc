<template>
  <div class="container">
    <h1>Contador</h1>
    <p>{{ 10 }}</p>
    <p>{{ 1 + 1 }}</p>
    <p>{{ this.numero }}<sup> 2 </sup> = {{ calCuadrado}}</p>
    <div>
        <button v-on:click="incrementar()">+1</button>
        <button v-on:click="decrementar()">-1</button>
    </div>

    <!--
    - Note: incluye proiedades reactivas y ..?
    - propiedades computadas: son una especie de metodo que se ejecuta una unica vez y cada vez que se llama
    ,toma el metodo y se guarda en cache. no puede tener el '()' como tiene un metodo ejempleo: 
    metodod: calCuadrado(), computed: calCuadrado
    - Directivas: Son funcionalidades que agregan comportamiento a mi pagina web, me permiten 
    gestionar eventos en mi pagina web y empiezan con 'b-' 
            
    -->


    <!-- 
    <p>{{ activo}}</p>
    <p>{{ usuario.edad}}</p>
    <p>{{ arreglo}}</p>

    <p>{{ true ? 'Es Verdadero' : 'Es Falso' }}</p>
    <p>{{ false ? 'Es Verdadero' : 'Es Falso' }}</p>-->
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero: 5,
      texto: "Jordy Chamba",
      activo: true,
      usuario: {
        nombre: "Jordy",
        edad: 25,
        profesion: "Estudiante",
      },
      arreglo: ["Azul"],
    };
  },
  methods: {
    calcularCuadrado() {
        console.log('Entro al método')
      return this.numero * this.numero;
    },
    incrementar(){
        this.numero++;
    },
    decrementar(){
        this.numero--;
    },
  },
  computed: {
    calCuadrado(){
        console.log('Entro a la propiedad computada')
      return this.numero * this.numero;
    },
  },
};
</script>

<style>
h1 {
  color: green;
  background: rgb(83, 83, 238);
}

p {
  background: rgb(236, 236, 117);
}
</style>
