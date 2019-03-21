<template>
  <div class="separacion">
    <b-media tag="li">
      <h5 class="md-12 sm-12">{{ pregunta }}</h5>
      <p class="md-12 sm-12">{{ msg }}</p>
    </b-media>
  </div>
</template>

<script>
export default {
  name: "mensaje",
  props: {
    msg: String,
    pregunta: String
  }
};
</script>

<style>
.separacion {
  margin-top: 10px;
  margin-right: 12px;
  width: 35%;
  display: inline-block;
  text-align: justify;
}
</style>
