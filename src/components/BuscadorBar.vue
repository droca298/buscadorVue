<template>
  <div class="buscador">
    <b-input-group>
      <b-form-input v-on:keyup.enter="emitBusqueda" v-model="texto" />
      <b-input-group-append>
        <b-button size="sm" v-on:click="emitBusqueda" text="Button" variant="success">
            Buscar
        </b-button>
      </b-input-group-append>
    </b-input-group>
  </div>
</template>

<script>

export default {
  name: "buscadorbar",
  data: function() {
    return {
      texto: ""
    };
  },
  methods : {
    emitBusqueda(){

      if (this.texto.length != 0){

        this.$emit('textoBusqueda', this.texto);
        this.texto = "";
      }
      
    },
  }
};
</script>

<style>

.buscador {

   width: 35%;
   margin: auto;

}

</style>
