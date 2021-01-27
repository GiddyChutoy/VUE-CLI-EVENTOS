<template>
    <div id="proposito2">
        <input type="text" v-model="contenidoInput" @keydown.enter="anadirProposito" name="nuevoProposito" id="nuevoProposito">
        <input type="button" value="Añadir" @click="anadirProposito">
    </div>
</template>

<script>
export default {
    name: 'proposito2',
    emits:["nuevoProposito"],
    data() {
        return {
            contenidoInput: "",
        }
    },
    methods: {
        anadirProposito() {

            if (this.contenidoInput == "") {

                alert("Debes escribir algo en el input");
            } else {

                let proposito = {
                    texto: this.contenidoInput,
                    done: false
                }
                this.contenidoInput= "";
                this.$emit("nuevoProposito", proposito);
            }
           
        },

    },

}
</script>