<template>
  <div class="navbar-menu body-sm-500">
    <Dropdown v-for="m in menu" :menuItem="m" />
  </div>
</template>

<script setup>
const menu = [
  {
    name: "Home",
    url: "/",
  },
  {
    name: "Shop",
    items: [
      {
        name: "Full catalog",
        url: "/shop",
      },
      {
        name: "Vegetables",
        url: "/shop/vegetables",
      },
      {
        name: "Fruits",
        url: "/shop/fruits",
      },
    ],
  },
  {
    name: "About Us",
    items: [
      {
        name: "Features",
        url: "/features",
      },
      {
        name: "Our team",
        url: "/our-team",
      },
    ],
  },
  {
    name: "Contact",
    url: "/contact",
  },
];
</script>

<style></style>
