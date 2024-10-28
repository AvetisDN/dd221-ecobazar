<template>
  <div class="hidden-overlay" v-if="show" @click="show = false"></div>
  <div class="select" :class="{ opened: show }">
    <NuxtLink
      v-if="menuItem.url"
      :to="menuItem.url"
      class="body-xs-400 nav-link"
      @click="toggleSelect"
    >
      {{ menuItem.name }}
    </NuxtLink>
    <h4
      v-else
      :to="menuItem.url"
      class="body-xs-400 nav-link dropdown"
      @click="toggleSelect"
    >
      {{ menuItem.name }}
    </h4>
    <ul v-if="menuItem.items && show">
      <li v-for="option in menuItem.items" @click="navigateTo(option.url)">
        {{ option.name }}
      </li>
    </ul>
  </div>
</template>

<script setup>
const props = defineProps(["menuItem"]);

const show = ref(false);

function toggleSelect() {
  show.value = !show.value;
}
function selectOption(opt) {
  selected.value = opt;
  show.value = false;
}
</script>

<style scoped>
.hidden-overlay {
  position: fixed;
  width: 100%;
  height: 100vh;
  top: 0;
  left: 0;
  z-index: 99;
}
.select {
  position: relative;
  padding: 2px 4px;
  &.opened {
    z-index: 100;
  }
  .nav-link {
    display: flex;
    align-items: center;
    gap: 6px;
    cursor: pointer;
    user-select: none;
    font-size: inherit;
    font-weight: inherit;
    &.dropdown::after {
      font-family: "icomoon" !important;
      content: "\e905";
    }
  }
  ul {
    list-style: none;
    padding: 0;
    position: absolute;
    left: 0;
    top: 100%;
    min-width: 100%;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.2);
    background-color: var(--gray-white);
    padding: 6px;
    li {
      padding: 4px 6px;
      cursor: pointer;
      transform: 0.3s ease;
      user-select: none;
      white-space: nowrap;
      &:hover {
        background-color: var(--green-100);
      }
      &.active {
        background-color: var(--green-50);
      }
    }
  }
}
</style>
