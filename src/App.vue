<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="header-title">
      Tripper Labs
    </div>
    <div class="header-items">
      More…
    </div>
  </header>
  <RouterView />
</template>

<style scoped>
header {
  z-index: 1000;
  width: 100%;
  height: 54px;
  max-width: none;
  border-radius: 0;
  top: 0px;
  display: flex;
  flex-direction: row;
  position: fixed;
}

.header-title,
.header-items {
  line-height: 58px;
  text-align: center;
  vertical-align: middle;
  margin: 0 12px;
}

.header-title {
  font-weight: 600;
}
</style>
