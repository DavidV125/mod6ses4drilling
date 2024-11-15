<script>

export default{
    props:{
        ObjetoImagen:{

    type: Object,
    required:true
}
    },
    data(){
        return{
            mensaje:'Descripción'
        }
    }}

</script>


<template>
    <div class="principal">
        <h2 v-html="mensaje"></h2>
        <section class="contenedorImagen">
            <img class="contenidoImagenes" v-bind:src="ObjetoImagen.ruta" v-bind:alt="ObjetoImagen.descripcion">

        </section>
        <section class="contenedorTexto">
            <p v-html="ObjetoImagen.descripcion"></p>
        </section>

    </div>

</template>

<style scoped>
    h2{
        color: black;
    }
    p{
        font-size:larger;
    }
    .principal{
        background-color: violet;
        margin:2%;
    }
    
    .contenidoImagenes{
        border-radius: 10%;
        width:400px;
        background-color:blue;
    }
</style>