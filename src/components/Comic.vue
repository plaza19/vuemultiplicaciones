<template>
    <div class="container">
        <h2>{{comic_props.titulo}}</h2>
        <h5>{{comic_props.descripcion}}</h5>
        <img :src=comic_props.imagen>
        <p>{{index}}</p>
        <br/>
        <button class="btn btn-secondary" @click="seleccionarFavorito()">Seleccionar Favorito</button>
        <button class="btn btn-warning" @click="modificarComic(comic_props)">Modificar</button>
        <button class="btn btn-danger" @click="eliminarComic()">Eliminar</button>
    </div>
</template>

<script>

    export default {
        name: "Comic",
        props: ["comic_props", "index"],
        methods: {
            seleccionarFavorito() {
                console.log("fsjf");
                console.log(this.comic_props);
                this.$emit("seleccionarFavorito", this.comic_props)
            },
            eliminarComic() {
                this.$emit("eliminarComic", this.index);
            },
            modificarComic(comic) {
                this.$emit("modificarComic", comic)
            }
        }
    }

</script>

<style scoped>
    div.container {
        border: 1px solid black;
        padding: 10px;
    }

    img {
        height: 200px;
        margin: 20px;
    }
</style>