<template>
  <div>
    <h1>Abundantum</h1>
    <p>Preguntame y te responderé.</p>

    <buscadorbar @textoBusqueda="getMensajes"></buscadorbar>

    <div class="row"></div>
    <div>
          <ul v-for="item in items" :key="item.id">
            <mensaje :pregunta="item.pregunta" :msg="item.respuesta"/>
            <div class="row"></div>
          </ul>
        </div>
  </div>
</template>

<script>
import buscadorbar from "./BuscadorBar.vue";
import mensaje from "./Mensaje.vue";

export default {
  name: "Inicio",
  props: {
    msg: String
  },
  data: function() {
    return {
      texto: "",
      items: [
        {"pregunta" : "Esto es una pruebas",
        "respuesta" : "Esto es una respuesta"},
      ]
    };
  },
  components: {
    buscadorbar,
    mensaje
  },
  methods: {
    getMensajes(pregunta) {
      this.items.unshift({
        pregunta: pregunta,
        respuesta: "Hola soy una respuesta de ejemplo xD"
      });
    },
  }
};
</script>
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
