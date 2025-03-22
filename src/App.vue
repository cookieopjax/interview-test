<script setup lang="ts">
import Sidebar from './components/Sidebar.vue';
import MainContent from './components/MainContent.vue';
</script>

<template>
  <div class="container">
    <Sidebar/>
    <div class="main-content-container">
      <MainContent/>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  display: flex;
  color: #333;
}

.main-content-container {
  /* 讓主內容區域佔滿剩餘空間，讓其內部滾動 */
  flex: 1;
  overflow-y: auto;
  height: 100vh;
}

@media (max-width: $tablet-breakpoint) {
  .container {
    height: auto;
  }
}

@media (max-width: $mobile-breakpoint) {
  .container {
    flex-direction: column;
    height: auto;
  }
}
</style>
