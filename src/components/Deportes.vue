<template>
    <div class="container">
        <h1>Deportes</h1>
        <h4  v-for="deporte in deportes" :key="deporte">
            <Deporte :nombre=deporte v-on:seleccionarFavoritoParent="seleccionarFavoritoParent"></Deporte>
        </h4>
        <h1>El deporte favorito es: {{favorito}}</h1>
        
        
    </div>
</template>

<script>
import Deporte from './Deporte.vue'



export default {
  components: { Deporte },
    name:"Deportes",
    data () {
        return {
            deportes: ["futbol", "baloncesto", "tenis", "badminton", "Ping-pong" ],
            favorito: ""
        }
    },
    methods: {
        seleccionarFavoritoParent(favorito) {
            console.log(favorito);
            this.favorito = favorito;
        }
    }
}

</script>