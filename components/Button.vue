<template>
  <button
    class="btn"
    :class="{
      'btn-sm': size === 'small',
      'btn-lg': size === 'large',
      'btn-ghost': type === 'ghost',
      'btn-border': type === 'border',
    }"
    :disabled="disabled"
  >
    {{ label }}
  </button>
</template>

<script setup>
defineProps(["label", "size", "type", "disabled"]);
</script>

<style>
:root {
  --primary: var(--semantic-success);
  --primary-hover: var(--semantic-success-dark);
  --primary-ghost: rgba(86, 172, 89, 0.1);
  --primary-ghost-hover: rgba(44, 116, 47, 0.2);
  --primary-contrast: var(--gray-white);
  --primary-ghost-contrast: var(--semantic-success);
  --primary-ghost-hover-contrast: var(--semantic-success-dark);
}
.btn {
  background-color: var(--primary);
  color: var(--primary-contrast);
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  padding: 14px 32px;
  font: 14px / 150% Poppins;
  font-weight: 600;
  border-radius: 99px;
  transition: 0.3s ease;
  &:hover {
    background-color: var(--primary-hover);
  }
}
.btn-sm {
  font: 12px / 130% Poppins;
  padding: 10px 24px;
  gap: 8px;
}
.btn-lg {
  font: 16px / 150% Poppins;
  gap: 16px;
  padding: 16px 40px;
}
.btn-ghost {
  background-color: var(--primary-ghost);
  color: var(--primary-ghost-contrast);
  &:hover {
    background-color: var(--primary-ghost-hover);
    color: var(--primary-ghost-hover-contrast);
  }
}
.btn-border {
  background-color: var(--gray-white);
  color: var(--primary);
  outline: 2px solid var(--primary);
  outline-offset: -2px;
  &:hover {
    background-color: var(--gray-white);
    color: var(--primary-hover);
    outline: 2px solid var(--primary-hover);
  }
}

.btn:disabled {
  background-color: var(--gray-50);
  color: var(--gray-300);
  outline: none;
  pointer-events: none;
}
</style>
