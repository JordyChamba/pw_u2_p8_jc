<template>
  <div class="container">
    <img
      src="https://yesno.wtf/assets/no/21-05540164de4e3229609f106e468fa8e7.gif"
      alt="No se pudo cargar"
    />
    <div class="container-2">
        /**/ */
        <div class="pregunta-container">   
            <input v-model="pregunta" type="text" placeholder="Hazme una pregunta" />
            <p>Recuerda Terminar con un signo de pregunta (?)</p>
            <h2>{{pregunta}}</h2>
            <h1>{{respuesta}}</h1>
        </div> 
      </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            pregunta: null,
            respuesta: null,
        };
    },
    //el watch me permite observar los cambios
    watch: {
        pregunta(value, oldValue){
            console.log("Valor actual:" + value);
             console.log("Valor anterior:" + oldValue);
        }
    }
};
</script>

<style scoped>
.container-2,
img {
  height: 100vh; /*Ocupado todo el alto*/
  width: 100vw; /*Ocupado todo el ancho*/
  max-height: 100%;
  max-width: 100%;
  position: fixed; /* No respesta la posicion, 
        pasa como si fuera una marca de agua*/
  left: 0px; /* Que empiece desde la izquiera*/
  top: 0px;
}

.container-2 {
  background-color: rgb(0, 0, 0, 0.5);
}

.pregunta-container {
    position: relative;
}

input {
    width: 350px;
    padding: 10px 15px;
    border-radius: 5px;
    border: none;
    font-size: 25px;
    margin-top: 80px;
    border-radius: 50px ;
}

input:focus {
    outline: none;
}

p{
    color: white;
    font-size: 25px;
}

h1, h2 {
    color: white;
}

h2 {
    margin-top: 120px;
}

</style>
