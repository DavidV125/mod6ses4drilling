<script>
import DescripcionScroll from './DescripcionScroll.vue';
export default{
    components:{
        DescripcionScroll
    },
    props:{
        arrImagenesScroll:{
            type:Array,
            required: true
        }

    },
    data(){
        return{
            mensaje:'Esto es el componente Scroll',
            objImagenTemp:{},
        }
    },
    methods:{
        enviarImagenHijo(objeto){
            this.objImagenTemp = objeto;
        }
    }
}
</script>

<template>
    <div>

        <section class="contenedoresGenerales">
            <h1 v-html="mensaje"></h1>
            <div class="contenedorImagenes">

                    <div class="contenedorScroll" >
                        <img class="contenidoImagenes" v-for="objetoImagen in arrImagenesScroll" 
                            v-bind:src="objetoImagen.ruta" 
                            v-bind:alt="objetoImagen.descripcion" 
                            v-on:click="enviarImagenHijo(objetoImagen)">    
                    </div>
    

            </div>

        </section>
        <section class="contenedoresGenerales">
            <DescripcionScroll
                v-bind:ObjetoImagenScroll="objImagenTemp"
            />
        </section>    
    </div>
</template>


<style scoped>
    div{
        background-color: yellow;
        margin:2%;
    }
    h1{
        color:brown;
    }

    .contenedorImagenes{
        max-width: auto;
    }

    .contenidoImagenes{
        width:100px;
    }

    .contenedoresGenerales{
        display: inline-block;
        width:48%;
    }

    .contenedorScroll{
        height:400px;
        background-color: chartreuse;
        margin:2%;
        overflow-y: scroll; /* agregamos scroll al div */
    }
</style>