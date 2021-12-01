<template>
  <header id="header" ref="bg">
    <h1>Photo Collection</h1>
  </header>
</template>

<script>
import { ref, onMounted } from "vue";

export default {
  setup() {
    const bg = ref(null);

    onMounted(() => {
      window.addEventListener("scroll", () => {
        bg.value.style.backgroundSize = 150 - +window.pageYOffset / 12 + "%";
        bg.value.style.opacity = 1 - +window.pageYOffset / 700 + "";
      });
    });

    return {
      bg,
    };
  },
};
</script>

<style>
header {
  position: relative;
  width: 100%;
  height: 80vh;
  background-color: rgb(234, 233, 248);
  background-image: url("../assets/images/collage.png");
  background-size: 120%;
  background-position: center;
  background-attachment: fixed;
  background-repeat: no-repeat;
  text-align: center;
  /* box-shadow: 0px 1px 5px 0px rgba(0,0,0,0.75); */
  box-shadow: 1px -5px 15px 0px rgba(204, 203, 203, 0.59) inset;
}

header h1 {
  padding-top: 2rem;
  font-size: 3em;
  font-weight: 800;
  letter-spacing: 0.07ex;
  color: #fcfcfc;
  text-shadow: 0 1px 0 #ccc, 0 2px 0 #c9c9c9, 0 3px 0 #bbb, 0 4px 0 #b9b9b9,
    0 5px 0 #aaa, 0 6px 1px rgba(0, 0, 0, 0.1), 0 0 5px rgba(0, 0, 0, 0.1),
    0 1px 3px rgba(0, 0, 0, 0.3), 0 3px 5px rgba(0, 0, 0, 0.2),
    0 5px 10px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.2),
    0 20px 20px rgba(0, 0, 0, 0.15);
  transition: all 300ms ease-out;
}
</style>