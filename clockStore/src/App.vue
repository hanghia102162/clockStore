<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import Login from "./components/Login.vue";
import Collections from "./components/Collections.vue";
import Nav from "./components/nav.vue";
import Workmanship from "./components/workmanship.vue";
import Cart from "./components/cart.vue";
import Footer from "./components/Footer.vue";
import { ref } from "vue";

const opentLogin = ref(false);
const opentHelloWord = ref(true);
const clickCollections = ref(false);
const clickWorkmanship = ref(false);
const clickCart = ref(false);
const header = ref(true);
const footer = ref(true);

const scrollTop = () => {
  window.scrollTo({
    top: 0,
    behavior: "smooth", // hoặc "auto" nếu không muốn animation
  });
};

const OpentLogin = () => {
  opentLogin.value = true;
  opentHelloWord.value = false;
  clickCollections.value = false;
  clickWorkmanship.value = false;
  clickCart.value = false;
  header.value = false;
  footer.value = false;
  scrollTop();
};

const OpenCollections = () => {
  clickCollections.value = true;
  opentHelloWord.value = false;
  opentLogin.value = false;
  clickWorkmanship.value = false;
  clickCart.value = false;
  scrollTop();
};
const OpentHelloWord = () => {
  opentHelloWord.value = true;
  opentLogin.value = false;
  clickCollections.value = false;
  clickWorkmanship.value = false;
  clickCart.value = false;
  header.value = true;
  footer.value = true;
  scrollTop();
};
const OpenWorkmanship = () => {
  clickWorkmanship.value = true;
  opentHelloWord.value = false;
  opentLogin.value = false;
  clickCollections.value = false;
  clickCart.value = false;
  scrollTop();
};
const OpenCart = () => {
  clickCart.value = true;
  clickWorkmanship.value = false;
  opentHelloWord.value = false;
  opentLogin.value = false;
  clickCollections.value = false;
  scrollTop();
};
</script>

<template>
  <Nav
    @accountClick="OpentLogin"
    @clickCollections="OpenCollections"
    @clickHome="OpentHelloWord"
    @clickWorkmanship="OpenWorkmanship"
    @clickCart="OpenCart"
    v-show="header"
  />
  <HelloWorld v-show="opentHelloWord" />
  <Login v-show="opentLogin" @back="OpentHelloWord" />
  <Collections v-show="clickCollections" />
  <Workmanship v-show="clickWorkmanship" />
  <Cart v-show="clickCart" />
  <Footer v-show="footer" />
</template>
