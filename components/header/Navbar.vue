<template>
  <div>
    <div class="container navbar">
      <HeaderNavbarMenu />
      <HeaderNavbarLogo />
      <HeaderNavbarRight :openCartMenu="openCartMenu" />
    </div>
  </div>
  <div class="overlay" v-if="cartMenu">
    <div class="shadow" @click="closeCartMenu"></div>
    <div class="cart-menu"></div>
  </div>
</template>

<script setup>
const cartMenu = ref(false);

const openCartMenu = () => (cartMenu.value = true);
const closeCartMenu = () => (cartMenu.value = false);
</script>

<style>
.overlay {
  position: fixed;
  width: 100%;
  height: 100vh;
  top: 0;
  left: 0;
  z-index: 100;
  .shadow {
    position: fixed;
    width: 100%;
    height: 100vh;
    top: 0;
    left: 0;
    background-color: rgba(0, 0, 0, 0.7);
  }
  .cart-menu {
    position: fixed;
    width: 100%;
    max-width: 456px;
    height: 100vh;
    top: 0;
    right: 0;
    background-color: var(--gray-white);
  }
}
</style>
