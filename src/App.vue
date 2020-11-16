<template>
  <div id="app">
    <img alt="vue logo" src="./assets/logo1.jpg">
    <h1>OPERACIONES MATEMÁTICAS</h1>
    <p><strong>Numero 1 : </strong><input type="number" v-model="num1" placeholder=" Ingrese Numero 1"></p>
    <p><strong>Numero 2 : </strong><input type="number" v-model="num2" placeholder=" Ingrese Numero 2"></p>
    <p> Multiplicacion : <strong>{{ calcularMultiplicar }} </strong></p>
     <p> Combinacion : <strong>{{ calcularCombinacion }} </strong></p>
    <p> Permutacion : <strong>{{ calcularPermutacion}} </strong></p>
    <p> Division : <strong>{{ calcularDividir }} </strong></p>
    <p> Residuo : <strong>{{ calcularResiduo }} </strong></p>
     
    <p> Potencia : <strong>{{ calcularPotencia }} </strong></p>
    <p> Resta : <strong>{{ calcularResta }} </strong></p>
    <p> Suma : <strong>{{ calcularSuma }} </strong> </p>
    <p> Raiz : <strong> {{ calcularRaiz }} </strong></p>
   
  
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      num1:1,
      num2:1
  
    }
  },
  computed: {
    calcularSuma () {
      let p = (parseInt(this.num1) + parseInt(this.num2))
      return p
    },
    
    calcularResta () {
      let p = (parseInt(this.num1) - parseInt(this.num2))
      return p
    },
    
    calcularMultiplicar () {
      let p = (parseInt(this.num1) * parseInt(this.num2))
      return p
    },
    
    calcularDividir () {
      if(this.num2==0 ){
        return "Tiene que ingresar un numero diferente de 0"
      }else{
      let p = (parseInt(this.num1) / parseInt(this.num2))
      return p
      }
    },
    
    calcularPotencia () {
      let p = Math.pow(parseInt(this.num1), parseInt(this.num2))
      return p
    },
    
    calcularResiduo () {
      if(this.num2==0 ){
        return "Tiene que ingresar un numero diferente de 0"
      }else{
      let p = (parseInt(this.num1) % parseInt(this.num2))
      return p
      }
    },
    
    calcularRaiz () {
      let p = Math.sqrt(parseInt(this.num1))
      return p
    },
    
    calcularPermutacion () {
  let r=1;
  let s=1;
  let resta;
  for (let i = this.num1; i > 0; i--) {
    r *=i;
  }
  resta = parseInt(this.num1)-parseInt(this.num2);
  for (let j = resta; j > 0; j--) {
    s *=j;
  }
  
      return (parseInt(r)/parseInt(s))
    },
    
    calcularCombinacion () {
     let r=1;
  let s=1;
  let t=1;
  let resta;
  for (let i = this.num1; i > 0; i--) {
    r *=i;
  }
  resta = parseInt(this.num1)-parseInt(this.num2);
  for (let j = resta; j > 0; j--) {
    s *=j;
  }
  for (let k = this.num2; k > 0; k--) {
    t *=k;
  }
      return  (parseInt(r)/(parseInt(s)*parseInt(t)))
    },
   
  }  
}
</script>

<style>
.red {
  color: red;
}
.green {
  color: green;
}
.blue {
  color: blue;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
p{
  font-size: 20px;
  
  color:darkgreen;
}
h1{
  color: darkblue;
  font-size: 40px;
}
</style>
