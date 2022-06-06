<template>
  <div id="app">
    <MenuPopout />
    <TitleSection id="title" class="section"/>
    <TitleSection id="title" class="section"/>
    <TitleSection id="title" class="section"/>
    <TitleSection id="title" class="section"/>
  </div>
</template>

<script>
import TitleSection from './sections/TitleSection.vue'

import MenuPopout from './components/MenuPopout.vue'

export default {
  name: 'App',
  components: { TitleSection, MenuPopout }
}
</script>

<style>
* {
  box-sizing: border-box;
  font-family: "Roboto", sans-serif;
}
body {
  margin: 0;
  padding: 0;
  background-color: #1c1c1c;
  color: white;
  position: relative;
  overflow-x: hidden;
  scroll-behavior: smooth;
}

.section {
  height: 100vh;
  width: 100%;
}
</style>