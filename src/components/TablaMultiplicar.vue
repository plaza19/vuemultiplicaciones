<template>
    <div>
        <h1>Tabla Multiplicar</h1>
        <label>Tabla del:</label>
        <input type="number" id="" v-model="numero"><br/>
        <button @click="calculartabla()">Calcular tabla</button>
         <hr/>
         <h1 v-if="res.length != 0">Resultado:</h1>
            <h3 v-for="multiplicacion in res" :key=multiplicacion>{{multiplicacion}}</h3>
         <!-- <h1 v-else>No se ha seleccionado un numero para calcular</h1>  -->
        
        <h1>Resultado en formato tabla</h1>
        <table style="margin:auto" class="table table-bordered">
            <thead>
                <th>multiplicacion</th>
            </thead>
            <tbody>
                <tr v-for="multiplicacion in res" :key="multiplicacion">
                    <td>{{multiplicacion}}</td>

                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>

export default {
    name : "TablaMultiplicar",
    data() {
        return {
            numero: 0,
            res: []
        }
        
    }, methods: {
        calculartabla() {
            this.res = [];
            for (var i=1; i<=10; i++) {
                this.res.push(i + "X" + this.numero + "=" + i*this.numero);
            }
        }
    }
}

</script>