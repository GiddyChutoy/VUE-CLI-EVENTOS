<template>
  <ul id="proposito1">
      <li v-for="(proposito, index) in arg1" :key="index" @dblclick="borrarProposito(index)">
          <del v-if="proposito.done == true">{{proposito.texto}}</del>
          <span v-else-if="proposito.done == false">{{proposito.texto}}</span>
          <span v-else>La lista está vacia</span>
          <input v-model="proposito.done" type="checkbox" name="done" id="done">
      </li>
  </ul>
</template>

<script>
  export default {
  name: 'proposito1',
  props:["arg1"],
  emits:["borrado"],

  methods: {
    borrarProposito(index){
      this.$emit("borrado", index);
    }
  },


}
</script>
