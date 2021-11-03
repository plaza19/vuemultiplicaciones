<template>
    <div class="container">
        <h1>El resultado de la suma de los hijos es: {{resultado}}</h1>
        
        <div v-for="numer in arrayNumeros" :key=numer>
            <SumaNumerosHijo :numeroProps=parseInt(numer) v-on:sumarNumero="sumarNumero"/>
        </div>
    </div>
</template>

<script>
import SumaNumerosHijo from './SumaNumerosHijo.vue'

    export default {
  components: { SumaNumerosHijo },
        name : "SumaNumerosParent",
        data () {
            return {
                resultado: 0,
                arrayNumeros : [2,4,6,34,5,7,3,23,5]
            }
        }, methods: {
            sumarNumero(numero) {
                this.resultado += numero;
            }
        }
    }

</script>