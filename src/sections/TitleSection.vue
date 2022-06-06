<template>
  <div class="titleSection">
    <TitleIntro class="titleIntro" />
  </div>
</template>

<script>
import TitleIntro from "../components/TitleIntro.vue"

export default {
  name: "TitleSection",
  components: { TitleIntro }
};
</script>

<style scoped>
.titleSection {
  display: flex;
  justify-content: center;
  align-items: center;
  background-image: url("../assets/topography.svg");
}
.titleIntro {
  width: 100vw;
}
</style>