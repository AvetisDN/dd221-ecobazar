<template>
  <div class="hidden-overlay" v-if="show" @click="show = false"></div>
  <div class="select" :class="{ opened: show }">
    <h4 class="body-xs-400" @click="toggleSelect">
      {{ selected }}
    </h4>
    <ul v-if="options && show">
      <li
        v-for="option in options"
        @click="selectOption(option)"
        :class="{ active: option === selected }"
      >
        {{ option }}
      </li>
    </ul>
  </div>
</template>

<script setup>
const props = defineProps(["options"]);

const selected = ref(props.options[0]);
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
  h4 {
    display: flex;
    align-items: center;
    gap: 6px;
    cursor: pointer;
    user-select: none;
    &::after {
      font-family: "icomoon" !important;
      content: "\e905";
    }
  }
  ul {
    list-style: none;
    padding: 0;
    position: absolute;
    right: 0;
    top: 100%;
    min-width: 100%;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.2);
    background-color: var(--gray-white);
    padding: 2px 0;
    li {
      padding: 2px 6px;
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
