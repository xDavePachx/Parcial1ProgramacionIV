<template>
  <div>
    <br>
    <br>
    <h1>BIENVENIDOS</h1>
    <br>
    <h2>Esta aplicacion es de una calculadora simple</h2>
    <br>
    <h3>Hecho por: Jorge Sorto y David Pacheco</h3>
    <br>
    <input v-model="vEntrada" type="string" placeholder="Ingrese un nombre y un apellido"/>
    <br>
    <b-button v-on:click="Guardarnombre" title="Guardar nombre">Guardar nombre</b-button>


  </div>
</template>
<script>
export default{
  name: "Home",
  data(){
    return{
      vEntrada: "",
      vNombre: ""
    }
  },
  methods:{
    Guardarnombre(){
      this.vNombre = this.vEntrada;
      console.log(this.vNombre)
    }
  }
}
</script>