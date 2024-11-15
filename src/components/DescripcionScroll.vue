<script>
export default{
    props:{
        ObjetoImagenScroll:{
            type: Object,
            required: true
        }
    },
    data(){
        return{
            mensaje:'Descripción Scroll'
        }
    }
}
</script>


<template>
    <div class="principal">

        <h2 v-html="mensaje"></h2>
        <section class="contenedorImagen">
            <img class="contenidoImagenes"  v-bind:src="ObjetoImagenScroll.ruta" v-bind:alt="ObjetoImagenScroll.descripcion">
        </section>
        <section class="contenedorTexto">
        <p v-html="ObjetoImagenScroll.descripcion"></p>
        </section>


    </div>
</template>

<style scoped>
    h2{
        color:goldenrod;
    }
    p{
        font-size:larger;
    }
    .principal{
        background-color:olivedrab;
        margin:2%;
    }
    .contenidoImagenes{
        width:100%;
    }

    .contenedorImagen{
        display: inline-block;
        width:69%;
        max-width: auto;
    }
    .contenedorTexto{
        display: inline-block;
        width:29%;
    }
</style>