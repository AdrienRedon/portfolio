<template>
  <header>
    <h1>
      Adrien REDON – {{ age }} ans<br />
      Développeur Web depuis {{ experience }} ans<br />
      Actuellement Lead Développeur Angular à Geolid
    </h1>
    <scroll-button href="#about" class="button"></scroll-button>
  </header>
</template>

<script>
import moment from "moment";
import ScrollButton from "../components/ScrollButton.vue";

export default {
  components: {
    ScrollButton,
  },
  computed: {
    age() {
      return moment().diff("1996-03-21", "years");
    },
    experience() {
      return moment().diff("2011-07-15", "years");
    },
  },
};
</script>

<style scoped>
header {
  display: -webkit-flex;
  display: -moz-flex;
  display: -ms-flex;
  display: -o-flex;
  display: flex;
  -webkit-flex-direction: column;
  -moz-flex-direction: column;
  -ms-flex-direction: column;
  -o-flex-direction: column;
  flex-direction: column;
  background: url(/assets/img/header.jpg) center no-repeat;
  background-size: cover;
  height: 100vh;
}

h1 {
  text-transform: uppercase;
  margin: auto;
  text-align: center;
  color: white;
  font-size: 24px;
}

@media screen and (min-width: 700px) {
  h1 {
    font-size: 32px;
  }
}

.button {
  margin: 0 auto;
}
</style>
