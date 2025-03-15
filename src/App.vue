<template>
  <div class="container animated">
    <Header class="fade-in" />
    <Main class="fade-in delay-1s" />
    <Service class="fade-in delay-2s" />
    <Slider class="fade-in delay-3s" />
  </div>
</template>

<script>
import Header from "./components/headere.vue";
import Main from "./components/main.vue";
import Service from "./components/OurServices.vue";
import Slider from "./components/slider.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
    Service,
    Slider,
  },
};
</script>

<style lang="scss">
@font-face {
  font-family: "Proxima Nova Condensed";
  src: url("./fonts/proximanova_black.otf") format("opentype"),
    url("./fonts/proximanova_black.ttf") format("truetype");
  font-weight: 900;
  font-style: normal;
}

@font-face {
  font-family: "Proxima Nova Condensed";
  src: url("./fonts/proximanova_blackit.otf") format("opentype");
  font-weight: 900;
  font-style: italic;
}

@font-face {
  font-family: "Proxima Nova Condensed";
  src: url("./fonts/proximanova_bold.otf") format("opentype");
  font-weight: bold;
  font-style: normal;
}

@font-face {
  font-family: "Proxima Nova Condensed";
  src: url("./fonts/proximanova_boldit.otf") format("opentype");
  font-weight: bold;
  font-style: italic;
}

@font-face {
  font-family: "Proxima Nova Condensed";
  src: url("./fonts/proximanova_extrabold.otf") format("opentype");
  font-weight: 800;
  font-style: normal;
}

@font-face {
  font-family: "Proxima Nova Condensed";
  src: url("./fonts/proximanova_light.otf") format("opentype");
  font-weight: 300;
  font-style: normal;
}

@font-face {
  font-family: "Proxima Nova Condensed";
  src: url("./fonts/proximanova_regular.ttf") format("truetype");
  font-weight: normal;
  font-style: normal;
}

body {
  font-family: "Proxima Nova Condensed", sans-serif;
  font-weight: normal;
  margin: 0;
  padding: 0;
}

* {
  box-sizing: border-box;
}

.container {
  max-width: 1250px;
  margin: 0 auto;
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

a {
  text-decoration: none;
}

@media (max-width: 1080px) {
  .container {
    max-width: 850px;
  }
}


@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.fade-in {
  opacity: 0; 
  animation: fadeInUp 2s ease-out forwards;
}


.delay-1s {
  animation-delay: 1s;
}
.delay-2s {
  animation-delay: 2s;
}
.delay-3s {
  animation-delay: 3s;
}
</style>
