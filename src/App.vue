<script setup lang="ts">
import Sidebar from './components/Sidebar.vue';
import MainContent from './components/MainContent.vue';
</script>

<template>
  <div class="container">
    <Sidebar/>
    <MainContent/>
  </div>
</template>

<style lang="scss" scoped>
.container {
  display: flex;
  height: 100vh;
  color: #333;
}



@media (max-width: $mobile-breakpoint) {
  .container {
    flex-direction: column;
    height: auto;
  }
}
</style>
