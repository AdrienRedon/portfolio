<template>
  <div id="app">
    <navbar id="menu"></navbar>
    <portfolio-header id="top"></portfolio-header>
    <about id="about"></about>
    <portfolio id="portfolio"></portfolio>
    <contact id="contact"></contact>
  </div>
</template>

<script>
  import About from './sections/About.vue';
  import Contact from './sections/Contact.vue';
  import Navbar from './components/Navbar.vue';
  import Portfolio from './sections/Portfolio.vue';
  import PortfolioHeader from './sections/PortfolioHeader.vue';

  export default {
    name: 'app',
    components: {
      About,
      Contact,
      Navbar,
      Portfolio,
      PortfolioHeader,
    }
  }
</script>

<style>
  html, body {
    margin: 0;
    padding: 0;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    font-size: 16px;
    box-sizing: border-box;
  }

  *, *:after, *:before {
    box-sizing: inherit;
  }

  h1, h2, h3 {
    text-align: center;
  }

  h2 {
    margin: 0;
    padding: 20px;
  }

  #menu {
    position: fixed;
      z-index: 9;
      left: 0;
      right: 0;
      bottom: 0;
  }

  @media screen and (min-width: 700px) {
    #menu {
      top: 0;
      bottom: auto;
    }
  }
</style>
