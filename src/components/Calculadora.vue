<template>
<div class="p-3" style="max-width: 400px; margin: 50px auto; background: #234">
  <Center><h2>CALCULADORA BASICA</h2></Center>
  <!-- Resultado: -->
    <div class="w-full rounded m-1 p-3 text-right lead font-weight-bold text-white bg-vue-dark">
      {{ valorCalculado || 0 }}
    </div>

    <!-- Botones de la calculadora -->
    <div class="row no-gutters">
      <div class="col-3" v-for="n in elementosCalculadora" :key="n">
        <div class="lead text-white text-center m-1 py-3 bg-vue-dark rounded hover-class" :class="{'bg-vue-green': ['C','*','/','-','+','%','='].includes(n)}" @click="action(n)">
          {{n}}
        </div>
      </div>
    </div>
</div>
</template>
<script>

export default {
  name:"Calculadora",
  props: {
    msg: String
  },
  data() {
    return{
      valorCalculado: '',
      elementosCalculadora: ['C','*','/','-',7,8,9,'+',4,5,6,'%',1,2,3,'=',0,'.'],
      operador: null,
      valorPrevio: '',
    }
  },
  methods: {
    action(n){
      /* annadir valor */
      if(!isNaN(n) || n === '.'){
        this.valorCalculado += n + '';
      }
      /* Limpiar todo */
      if(n === 'C'){
        this.valorCalculado = '';
      }
      /* Calcular porcentaje */
      if(n === '%'){
        this.valorCalculado = this.valorCalculado / 100 + '';
      }
      /* Operadores... */
      if(['/','*','-','+'].includes(n)){
        this.operador = n;
        this.valorPrevio = this.valorCalculado;
        this.valorCalculado = '';
      }
      /* Calcular los resultados usando funcion EVAL */
      if(n === '='){
        this.valorCalculado = eval(
          this.valorPrevio + this.operador + this.valorCalculado
        );
        this.valorPrevio = '';
        this.operador = null;
      }
    
    }
  }
}
</script>

<style scoped>
  .bg-vue-dark {
    background: #31475e;
  }
  .hover-class:hover {
    cursor: pointer;
    background: #3D5875;
  }
  .bg-vue-green {
    background: #3fb984;
  }
</style>