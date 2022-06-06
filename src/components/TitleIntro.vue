<template>
  <main>
    <div class="title">
      <h1 ref="greeting">Hi there! I'm</h1>
      <h2 ref="name">Ryan Widmer.</h2>
      <div ref="profession" class="title-wrapper">
        <h3>Engineering Manager</h3>
      </div>
    </div>
    <aside class="hero-image">
      <img
        ref="img"
        src="../assets/my-photo-square.jpg"
        alt="Picture of Ryan"
      />
    </aside>
  </main>
</template>

<script>
export default {
  name: "TitleIntro",
};
</script>

<style scoped>
main {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}
h1 {
  margin: 0;
  font-weight: 300;
  font-size: clamp(32px, 4vw, 52px);
}
h2 {
  margin: 0;
  font-size: clamp(62px, 8vw, 140px);
  font-weight: 900;
}
h3 {
  text-align: center;
  font-size: clamp(20px, 2.8vw, 44px);
  margin: 0;
  font-weight: 700;
}
img {
  border: 10px solid white;
  border-radius: 50%;
  width: clamp(200px, 20vw, 20vw);
  filter: grayscale(30%);
  transition: all 0.4s ease-in-out;
  cursor: pointer;
}
img:hover {
  transform: scale(1.1);
}
.title-wrapper {
  cursor: pointer;
  margin-top: 2em;
  padding: 1em;
  width: 100%;
  background-color: white;
  color: #1c1c1c;
  transition: all 0.1s ease-in-out;
  /* z-index: 2; */
  border-radius: 50px;
}
.title-wrapper:hover {
  background-color: #23c4c4;
}
</style>
