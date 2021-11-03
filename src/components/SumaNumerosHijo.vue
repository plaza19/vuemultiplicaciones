<template>
    <div class="container" style="border: 1px solid black">
        <h1>Soy el número: {{num}}</h1>
        <button @click="sumarNumero()" class="btn btn-secondary">+1</button>
    </div>
</template>

<script>

    export default {
        name : "SumaNumerosHijo",
        data () {
            return {
                num :  this.numeroProps
            }
        },
        props : ["numeroProps"],
        methods: {
            sumarNumero() {
                this.num += 1;
                this.$emit("sumarNumero", 1)
            }
        }, mounted () {
            this.$emit("sumarNumero", parseInt(this.num));
        }
    }

</script>

<style scoped>
    div.container {
        padding: 10px;
    }
</style>