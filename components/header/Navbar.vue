<template>
  <div>
    <div class="container navbar">
      <HeaderNavbarMenu />
      <HeaderNavbarLogo />
      <HeaderNavbarRight :openCartMenu="openCartMenu" />
    </div>
  </div>
  <div class="overlay" :class="{ visible: cartMenu }">
    <div class="shadow" @click="closeCartMenu"></div>
    <div class="cart-menu">
      <HeaderNavbarCartMenu :closeCartMenu="closeCartMenu" />
    </div>
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
  z-index: -1;
  .shadow {
    position: fixed;
    width: 100%;
    height: 100vh;
    top: 0;
    left: 0;
    background-color: rgba(0, 0, 0, 0.7);
    opacity: 0;
    transition: 0.3s ease;
  }
  .cart-menu {
    position: fixed;
    width: 100%;
    max-width: 456px;
    height: 100vh;
    top: 0;
    right: -456px;
    opacity: 0;
    background-color: var(--gray-white);
    transition: 0.3s ease;
  }
}
.overlay.visible {
  z-index: 100;
  .shadow {
    opacity: 1;
  }
  .cart-menu {
    right: 0;
    opacity: 1;
  }
}
</style>
