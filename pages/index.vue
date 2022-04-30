<template>
  <div id="app-child" :class="mode">
    <MenuComp/>
    <div class="introduction">
      <HeaderComp :mode="mode" @toggle="toggle"/>
      <TitleComp/>
    </div>
    <TitlesComp/>
    <AboutComp/>
    <WebWork/>
    <DesignWork/>
    <ContactComp/>
    <FooterComp/>
  </div>
</template>

<script>
  import MenuComp from "../components/MenuComp.vue";
  import HeaderComp from "../components/HeaderComp.vue";
  import TitleComp from "../components/TitleComp.vue";
  import TitlesComp from "../components/TitlesComp.vue";
  import AboutComp from "../components/AboutComp.vue";
  import WebWork from "../components/WebWork.vue";
  import DesignWork from "../components/DesignWork.vue";
  import ContactComp from "../components/ContactComp.vue";
  import FooterComp from "../components/FooterComp.vue";
  export default {
    name: 'App',
    components: {
      MenuComp,
      HeaderComp,
      TitleComp,
      TitlesComp,
      AboutComp,
      WebWork,
      DesignWork,
      ContactComp,
      FooterComp
    },
    data() {
      return {
        mode: 'dark'
      }
    },
    methods: {
      toggle() {
        (this.mode === 'dark') ? this.mode = 'light': this.mode = 'dark';
      }
    }
  }
</script>

<style lang="scss">
@import "@/assets/scss/_vars.scss";

  html {
    scroll-behavior: smooth;
  }

  body {
    margin: 0;
    color: $dark-background-color;

    * {
      transition: all 0.3s ease-in-out;
    }

  }

  #app-child {
    font-family: $font-family, $font-family-fallback;
    padding: 65px 50px;
    position: relative;

    div {
      max-width: 512px;
    }

  }
  .dark {
    background-color: $dark-background-color;

    h1, h2, h3, span, footer, a p {
      color: $dark-title-color;
    }

    #menu .container .burger, #menu .container ul {
      background-color: $dark-menu-color;
    }

  }

  .light {
    background-color: $light-background-color;
    color: $light-title-color;
  }

  h1 {
    font-size: $mobile-h1;
    margin-bottom: 0;
    line-height: 17.5px;
  }

  h2 {
    font-size: $mobile-h2;
    margin: 20px 0px 10px 0px;
  }

  h3 {
    font-size: $mobile-h3;
    font-weight: 500;
  }

  p, a {
    font-size: $mobile-p;
  }

  p {
    color: $font-color;
  }

  @media screen and (min-width:1024px) {

    .introduction {
      display: grid;
      grid-template-columns: 215px 1fr;
      grid-gap: 50px;
    }

    #app-child {

      div {
        max-width: 1087px;
      }

      .titles {
        max-width: calc(1080px - 265px);
      }

    }

    h1 {
      font-size: $desktop-h1;
    }

    h2 {
      font-size: $desktop-h2;
      margin: 0px;
    }

    h3 {
      font-size: $desktop-h3;
    }

    p, a {
      font-size: $desktop-p;
    }

  }
</style>
