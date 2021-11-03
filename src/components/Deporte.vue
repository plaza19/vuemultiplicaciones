<template>
    <div class="container">
        <!-- <h1>Deporte</h1> -->
        <h2>{{nombre}}</h2>
        <button class="btn btn-secondary" @click="seleccionarFavorito(nombre)">seleccionarFavorito</button>
    </div>
</template>

<script>

export default {
    name:"Deporte",
    props : ["nombre"],
    methods: {
        seleccionarFavorito(nombreFav) {
            // console.log(nombreFav);
            // this.favorito = nombreFav;
            this.$emit("seleccionarFavoritoParent", nombreFav);    
            
        }
    }, 
    data () {
        return {
            favorito : ""
        }
    }
}

</script>