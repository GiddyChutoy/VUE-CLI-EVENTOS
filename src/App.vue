<template>
  <div id="barras">
    <h1 :class="[propositos.length > 3 ? 'libertario' : '']">
      Propósitos de año nuevo
    </h1>

    <proposito1 :arg1="propositos" @borrado="borrarProposito"></proposito1>

    <br />

    <proposito2 @nuevoProposito="anadirProposito"></proposito2>

    <br />

    <input
      type="button"
      v-on:click="borrarAbsolutamenteTodo"
      value="Borrar todo"
    />
  </div>
</template>

<script>
import proposito1 from "./components/proposito1.vue";
import proposito2 from "./components/proposito2.vue";

export default {
  name: "barras",
  components: {
    proposito1,
    proposito2,
  },
  data() {
    return {
      propositos: [
        {
          texto: "Ir al gym",
          done: false,
        },
        {
          texto: "Conocer a la hija de Willyrex",
          done: false,
        },
        {
          texto: "Flexear muchísimo",
          done: false,
        },
      ],

      claseVerde: "verdeDerechaGS",
      claseRoja: "rojoFS",
      claseAmarilla: "libertario",
      claseVerdeFuerte: "rosaVerdeOCentrado",

    };
  },

  methods: {
      borrarProposito(index){
        this.propositos.splice(index, 1)
      },

      borrarAbsolutamenteTodo(){
          this.propositos = []
      },

      anadirProposito(proposito){
        this.propositos.push(proposito);
      }
  },
};
</script>

<style>
.verdeDerechaGS {
  color: green;
  text-align: right;
  font-family: "Gill Sans";
}

.rojoFS {
  color: red;
  font-family: fantasy;
  list-style-type: square;
}
.libertario {
  color: yellow;
  background-color: black;
  text-align: center;
}

.rosaVerdeOCentrado {
  color: pink;
  background-color: darkgreen;
  text-align: center;
}
</style>
