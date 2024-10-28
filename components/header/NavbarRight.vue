<template>
  <div class="navbar-right">
    <a href="tel:2195550114" class="call-now body-sm-600">
      <i class="icon-phone-call"></i>
      (219) 555-0114
    </a>
    <div class="icons">
      <button>
        <i class="icon-search"></i>
      </button>
      <button>
        <i class="icon-heart"></i>
      </button>
      <button @click="openCartMenu">
        <i class="icon-bag"></i>
        <span class="badge">22</span>
      </button>
      <button>
        <i class="icon-user"></i>
      </button>
    </div>
  </div>
</template>

<script setup>
defineProps(["openCartMenu"]);
</script>

<style>
.navbar-right {
  display: flex;
  gap: 40px;
  align-items: center;
}
.call-now {
  display: flex;
  align-items: center;
  gap: 12px;
  i {
    font-size: 26px;
  }
}
.icons {
  font-size: 28px;
  button {
    position: relative;
    .badge {
      position: absolute;
      top: -1px;
      right: -1px;
      border: 1px solid var(--gray-white);
      background-color: var(--semantic-success-dark);
      color: var(--gray-white);
      width: 22px;
      height: 22px;
      display: flex;
      align-items: center;
      justify-content: center;
      line-height: 1;
      border-radius: 50%;
      font-size: 10px;
      font-weight: 500;
    }
  }
}
</style>
