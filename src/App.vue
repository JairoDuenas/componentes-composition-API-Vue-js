<template>
  <button @click="show = !show">Menu</button>
  <transition name="fade">
    <Menu v-show="show" />
  </transition>
  <Modal />
  <Hola />
  <div>{{ algo }}</div>
  <HelloWorld />
</template>

<script>
import { defineAsyncComponent } from "vue";
import Menu from "./components/Menu.vue";
import Modal from "./components/Modal.vue";
import Hola from "./components/Hola.vue";
import base from "./mixins/base";

const HelloWorld = defineAsyncComponent(() =>
  import("./components/HelloWorld.vue")
);

export default {
  name: "App",
  mixins: [base],
  components: {
    HelloWorld,
    Menu,
    Modal,
    Hola,
  },
  data() {
    return {
      show: false,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.fade-leave-active,
.fade-enter-active {
  transition: opacity 0.5s ease;
}
</style>
