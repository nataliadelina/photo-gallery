<template>
  <section class="collection">
    <h2>explore collection by scrolling down</h2>
    <div class="collectionBx">
      <div class="box" v-for="(el, index) in gallery" :key="index">
        <div
          class="imgBx"
          :class="{ active: el.active }"
          @click="toggleActiveImg(index)"
        >
          <div class="imgArounder">
            <img :src="require(`@/assets/${el.img}`)" :alt="el.details" />
          </div>
          <p class="close">click again to close</p>
          <div class="content">
            <h3>{{ el.title }}</h3>
            <p>{{ el.details }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Vue from "vue";
import galleryData from "../../data/gallery.json";

export default {
  data() {
    return {
      gallery: galleryData,
    };
  },
  methods: {
    toggleActiveImg(index) {
      let item = this.gallery[index];
      item.active = !item.active;
      Vue.set(this.gallery, index, item);
    },
  },
};
</script>

<style>
.collectionBx {
  width: 80vw;
  min-height: 100vh;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  margin: 1rem auto;
  margin-bottom: 5rem;
}

h2 {
  padding-top: 1rem;
  font-weight: bold;
  color: #b1b1b4;
}

section .box {
  position: relative;
  width: 200px;
  height: 200px;
  margin: 1rem;
  background-color: rgb(12, 6, 20);
  overflow: hidden;
  box-shadow: -2px 3px 8px 0px rgba(0, 0, 0, 0.59);
}

section .box {
  position: relative;
  width: 200px;
  height: 200px;
  margin: 1rem;
  background-color: rgb(12, 6, 20);
  overflow: hidden;
  box-shadow: -2px 3px 8px 0px rgba(0, 0, 0, 0.59);
}

section .box .imgBx {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(230, 226, 235, 0.7);
}

section .box .imgBx.active {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1000;
}

section .box .imgBx img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

section .box .imgBx.active img {
  position: fixed;
  top: 50px;
  left: 50px;
  right: 50px;
  bottom: 50px;
  width: calc(100% - 100px);
  height: calc(100% - 100px);
  object-fit: cover;
}

section .box .imgBx p,
h3 {
  opacity: 0;
  visibility: hidden;
}

section .box .imgBx.active p,
h3 {
  opacity: 1;
  visibility: visible;
  text-align: center;
}

section .box .imgBx .content {
  position: absolute;
  left: 50px;
  right: 50px;
  bottom: 50px;
  opacity: 0;
  visibility: hidden;
  background: rgba(230, 230, 230, 0.5);
  color: rgb(59, 59, 59);
  padding: 1rem;
  transform: translateY(100%);
  box-shadow: -2px 3px 8px 0px rgba(0, 0, 0, 0.59);
}

section .box .imgBx.active .content {
  opacity: 1;
  visibility: visible;
  transform: translateY(0);
  transition: 0.5s;
}

.close {
  padding-top: 1rem;
}
</style>