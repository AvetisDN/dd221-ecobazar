<template>
  <div class="header_topline">
    <div class="container topline body-xs-400">
      <div class="left">
        <i class="icon-map-pin"></i>
        Store Location: Lukaku 34, Harare, Zimbabwe
      </div>
      <div class="right">
        <Select :options="['Eng', 'Ru']" />
        <Select :options="['USD', 'RUR']" />
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup></script>

<style></style>
