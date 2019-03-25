<template>
  <div id="bg">
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

    <div id="chat">
      <b-embed
        type="iframe"
        id="chat-embebed"
        aspect="4by3"
        src="https://console.dialogflow.com/api-client/demo/embedded/5570cfa9-df4e-4a81-a1f6-fd011cd66b73"
      />
    </div>
  </div>
</template>

<script>
const $ = require('jquery');
window.$ = $;
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
        { pregunta: "Esto es una prueba", respuesta: "Esto es una respuesta" }
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
        respuesta: "Hola, soy una respuesta de ejemplo. xD"
      });
    }
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

#chat {
  width: 50%;
  margin: auto;
  height: 600px;
}
</style>
