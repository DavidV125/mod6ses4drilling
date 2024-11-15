<script>
import Descripcion from './Descripcion.vue';

export default {
  components: {
    Descripcion
  },
  props: {
    arrAlbumes: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      mensaje: 'Top 6 de álbumes más escuchados de 2024',
      posicionActualImagen:0,
            posicionFinalImagen:0,
            arrAlbumesTemp:[],
            objImagenTemp:{},
            primeraCarga:false 
    };
  },
  methods:{
        cargarDosPrimeras(){

            this.posicionFinalImagen = this.posicionActualImagen + 2;
            for(let i= this.posicionActualImagen; i < this.posicionFinalImagen; i++){
                this.arrAlbumesTemp.push(this.arrAlbumes[i]);
            }
            this.primeraCarga = !this.primeraCarga;

        },
        cargarDosMas(){
            console.log('Posicion Final Imagen antes del IF:',this.posicionFinalImagen);
            this.arrAlbumesTemp = [];
            if(this.posicionFinalImagen<=4){
                
                this.posicionActualImagen = this.posicionFinalImagen;
                this.posicionFinalImagen = this.posicionActualImagen + 2;
                for(let i= this.posicionActualImagen; i < this.posicionFinalImagen; i++){
                    this.arrAlbumesTemp.push(this.arrAlbumes[i]);
                }
            }
            else{
                this.posicionActualImagen=0;
                this.posicionFinalImagen = this.posicionActualImagen + 2;
                for(let i= this.posicionActualImagen; i < this.posicionFinalImagen; i++){
                    this.arrAlbumesTemp.push(this.arrAlbumes[i]);
                }

            }
            console.log('Posicion Final Imagen DESPUÉS del IF:',this.posicionFinalImagen);

        },

        cargarDosMenosOriginal(){
            console.log('Posicion Final Imagen antes del IF:',this.posicionFinalImagen);
            this.arrAlbumesTemp = [];
            if(this.posicionFinalImagen<=6 && this.posicionFinalImagen>0){
                console.log('ingresa al if');
                this.posicionActualImagen = this.posicionFinalImagen;
                this.posicionFinalImagen = this.posicionActualImagen - 2;
                for(let i= this.posicionActualImagen-1; i >= this.posicionFinalImagen; i--){
                    console.log(i);

                    this.arrAlbumesTemp.push(this.arrAlbumes[i]);
                }
            }
            else{
                console.log('ingresa al else');                
                this.posicionFinalImagen =  4;
                this.posicionActualImagen=6;
                for(let i= this.posicionActualImagen-1; i >= this.posicionFinalImagen; i--){
                    this.arrAlbumesTemp.push(this.arrAlbumes[i]);
                }

            }
            console.log('Posicion Final Imagen DESPUÉS del IF:',this.posicionFinalImagen);

        },

        cargarDosMenos(){
            console.log('Posicion Final Imagen antes del IF:',this.posicionFinalImagen);
            this.arrAlbumesTemp = [];
            if(this.posicionFinalImagen<=2 ){
                console.log('ingresa al if');
                this.posicionActualImagen = 4;
                this.posicionFinalImagen = this.posicionActualImagen + 2;
                for(let i= this.posicionActualImagen; i < this.posicionFinalImagen; i++){
                    console.log(i);
                    this.arrAlbumesTemp.push(this.arrAlbumes[i]);
                }
            }
            else{
                console.log('ingresa al else');                
                //this.posicionFinalImagen =  4;
                //this.posicionActualImagen=6;
                //for(let i= this.posicionActualImagen-1; i >= this.posicionFinalImagen; i--){
                    //this.arrImagenesTemp.push(this.arrImagenes[i]);
                //}


                this.posicionActualImagen = this.posicionFinalImagen-4;
                this.posicionFinalImagen = this.posicionActualImagen + 2;
                
                
                for(let i= this.posicionActualImagen; i < this.posicionFinalImagen; i++){
                    console.log(i);
                    this.arrAlbumesTemp.push(this.arrAlbumes[i]);
                }

            }
            console.log('Posicion Final Imagen DESPUÉS del IF:',this.posicionFinalImagen);

        },
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

              <div v-if="!primeraCarga">
                    <button v-on:click="cargarDosPrimeras">Cargar Imagenes</button><br>
                </div>
                

                <div v-if="primeraCarga">
                    <button v-on:click="cargarDosMenos">Atras</button>
                    <button v-on:click="cargarDosMas">Adelante</button>
                </div>


                <div class="limiteBotones" v-for="objetoImagen in arrAlbumesTemp" v-on:click="enviarImagenHijo(objetoImagen)" >
                    <img class="contenidoImagenes"  v-bind:src="objetoImagen.ruta" v-bind:alt="objetoImagen.descripcion">
                </div>

            </div>

        </section>
        <section class="contenedoresGenerales">
            <Descripcion 
                v-bind:ObjetoImagen="objImagenTemp"
            />
        </section>    
    </div>
</template>


<style scoped>
    div{
        background-color: whitesmoke;
        margin:2%;
    }
    h1{
        color:black;
    }

    .contenedorImagenes{
        border-radius: 10%;
        max-width: 100px;
        background-color:red;
    }

    .contenidoImagenes{
        border-radius: 10%;
        width:100px;
        background-color:blue;
    }

    .contenedoresGenerales{
        display: inline-block;
        border-radius: 10%;
        width:48%;
        background-color:yellow;
    }
</style>