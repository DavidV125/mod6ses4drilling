<script>
import Albumes from './components/Albumes.vue';
import Titulo from './components/Titulo.vue';
import ScrollAlbumes from './components/ScrollAlbumes.vue';
export default{
  components:{
    Albumes,
    Titulo,
    ScrollAlbumes
  },
  data(){
    return{
      arregloDatos:[
      {
          ruta:'./src/assets/brat.jpg',
          descripcion:'<b>Charli XCX - <i>Brat</i> (2024)</b><br> Un álbum enérgico con influencias punk-pop, donde Charli XCX explora sonidos crudos y letras honestas sobre juventud y rebeldía.'
        },
        {
          ruta:'./src/assets/indo.jpg',
          descripcion:'<b>Indochine - <i>3</i> (1985)</b><br> Un trabajo de new wave y rock francés que define el sonido único de Indochine, abordando temas poéticos y melancólicos.'
        },
      {
          ruta:'./src/assets/peril.jpg',
          descripcion:'<b>Indochine - <i>Le Péril Jaune</i> (1983)</b><br> Este álbum captura la intensidad y el misticismo de los años 80, con letras introspectivas y sonidos oscuros característicos de Indochine.'
        },
        {
          ruta:'./src/assets/blue.jpg',
          descripcion:'<b>Madonna - <i>True Blue</i> (1986)</b><br> Este icónico álbum mezcla pop y dance, consolidando a Madonna como una fuerza creativa con éxitos inolvidables y vibrantes temas románticos.'
        },



        {
          ruta:'./src/assets/man.jpg',
          descripcion:'<b>Kraftwerk - <i>The Man-Machine</i> (1978)</b><br> Pionero del synth-pop, este álbum presenta temas futuristas y sonidos robóticos, marcando un hito en la música electrónica.'
        },
        {
          ruta:'./src/assets/trst.jpg',
          descripcion:'<b>TR/ST - <i>tr/st</i> (2012)</b><br> Un álbum debut oscuro y cautivador, con una mezcla de synth-pop y post-punk. Sus ritmos hipnóticos y letras melancólicas crean una atmósfera intensa y única en cada pista.'
        },


      ],
      arregloDatosScroll:[ //nuevo arreglo para scroll
      {
          ruta:'./src/assets/brat.jpg',
          descripcion:'<b>Charli XCX - <i>Brat</i> (2024)</b><br> Un álbum enérgico con influencias punk-pop, donde Charli XCX explora sonidos crudos y letras honestas sobre juventud y rebeldía.'
        },
        {
          ruta:'./src/assets/indo.jpg',
          descripcion:'<b>Indochine - <i>3</i> (1985)</b><br> Un trabajo de new wave y rock francés que define el sonido único de Indochine, abordando temas poéticos y melancólicos.'
        },
      {
          ruta:'./src/assets/peril.jpg',
          descripcion:'<b>Indochine - <i>Le Péril Jaune</i> (1983)</b><br> Este álbum captura la intensidad y el misticismo de los años 80, con letras introspectivas y sonidos oscuros característicos de Indochine.'
        },
        {
          ruta:'./src/assets/blue.jpg',
          descripcion:'<b>Madonna - <i>True Blue</i> (1986)</b><br> Este icónico álbum mezcla pop y dance, consolidando a Madonna como una fuerza creativa con éxitos inolvidables y vibrantes temas románticos.'
        },



        {
          ruta:'./src/assets/man.jpg',
          descripcion:'<b>Kraftwerk - <i>The Man-Machine</i> (1978)</b><br> Pionero del synth-pop, este álbum presenta temas futuristas y sonidos robóticos, marcando un hito en la música electrónica.'
        },
        {
          ruta:'./src/assets/trst.jpg',
          descripcion:'<b>TR/ST - <i>tr/st</i> (2012)</b><br> Un álbum debut oscuro y cautivador, con una mezcla de synth-pop y post-punk. Sus ritmos hipnóticos y letras melancólicas crean una atmósfera intensa y única en cada pista.'
        },


      ]
    }
  },
  methods:{

  }

}
</script>

<template>
  <div class="componentePadre">
      <header>
        <h1>Resumen musical 2024</h1>
      </header>

      <div class="componenteTitulo">
          <Titulo mensaje="Esto es solo un resumen de los álbumes que más he escuchado este año" />
      </div>
      <hr>

      <div class="divAlbumes">
        <Albumes
            v-bind:arrAlbumes="arregloDatos"
        />
      </div>

      <div>
        <ScrollAlbumes
            v-bind:arrImagenesScroll="arregloDatosScroll"
        />
      </div>

      <footer>
        <p>Elaborado por <b>David Villacura</b></p>
      </footer>
  </div>


</template>

<style scoped>
  .componenteHijo{


    border-radius: 10%;
    
  }
  .componentePadre{
    background-color: gainsboro;
    border-radius: 5%;
  }
  .divAlbumes{
    background-color: orange;
    border-radius: 5%;
  }
</style>