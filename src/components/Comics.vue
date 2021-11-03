<template>
    <div class="container">
        <h1>Comics</h1>
        <div id="divFavorito" v-if="favorito != null">
            <h2>{{favorito.titulo}}</h2>
            <h5>{{favorito.descripcion}}</h5>
            <img :src=favorito.imagen>
        </div>
        <div v-for="comic in comics" :key=comic class="container">
            <Comic :comic_props="comic" v-on:seleccionarFavorito="seleccionarFavorito" v-on:eliminarComic="eliminarComic">{{index_aux +1}}</Comic>
        </div>
    </div>
</template>

<script>
import Comic from './Comic.vue'

export default {
  components: { Comic },
    name: "Comics",
    data () {
        return {
            comics: [
             {
             titulo: "Spiderman",
             imagen:
            "https://3.bp.blogspot.com/-i70Zu_LAHwI/T290xxduu-I/AAAAAAAALq8/8bXDrdvW50o/s1600/spiderman1.jpg",
             descripcion: "Hombre araña"
            },
            {
             titulo: "Wolverine",
             imagen:
            "https://images-na.ssl-images-amazon.com/images/I/51c1Q1IdUBL._SX259_BO1,204,203,200_.jpg",
             descripcion: "Lobezno"
            },
            {
             titulo: "Guardianes de la Galaxia",
             imagen:
            "https://cdn.normacomics.com/media/catalog/product/cache/1/thumbnail/9df78eab33525d08d6e5fb8d27136e95/g/u/guardianes_galaxia_guadianes_infinito.jpg",
             descripcion: "Yo soy Groot"
            },
            {
             titulo: "Avengers",
             imagen:
            "https://d26lpennugtm8s.cloudfront.net/stores/057/977/products/ma_avengers_01_01-891178138c020318f315132687055371-640-0.jpg",
             descripcion: "Los Vengadores"
            },
            {
             titulo: "Spawn",
             imagen:
            "https://i.pinimg.com/originals/e1/d8/ff/e1d8ff4aeab5e567798635008fe98ee1.png",
             descripcion: "Al Simmons"
            },
            {
             titulo: "Batman",
             imagen:
            "https://www.comicverso.com/wp-content/uploads/2020/06/The-Killing-Joke-657x1024.jpg",
             descripcion: "Murcielago"
            }
   ],
   favorito : null,
   index_aux : 0
        }
    },
    methods: {
        seleccionarFavorito(selectedComic) {
            this.favorito = selectedComic;
            console.log(selectedComic);
        }
    }
}


</script>

<style scoped>
    #divFavorito {
        border: 1px solid black;
        background-color: lightcoral;
        padding: 10px;
    }
    img {
        height: 200px;
    }
</style>

