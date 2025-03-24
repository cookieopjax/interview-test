<script setup lang="ts">
import BirdLogo from './BirdLogo.vue';
import { ref } from 'vue';

interface NavItem {
  id: number;
  text: string;
  isActive: boolean;
}

const navItems = ref<NavItem[]>([
  { id: 1, text: '白頭翁的特性', isActive: true},
  { id: 2, text: '白頭翁的故事', isActive: false},
  { id: 3, text: '白頭翁的家園', isActive: false},
  { id: 4, text: '白頭翁的鳴聲', isActive: false}
])

const handleNavClick = (index: number) => {
  navItems.value.forEach((item, i) => {
    item.isActive = i === index;
  });
}

const isCollapsed = ref(true);

</script>

<template>
  <nav class="sidebar">
    <div class="sidebar-header">
      <div class="hamburger-container">
        <img src="/hamburger.png" alt="hamburger" class="hamburger" @click="isCollapsed = !isCollapsed">
      </div>
      <div class="title">白頭翁不吃小米</div>
      <div class="logo">
        <BirdLogo/>
      </div>
    </div>
    <div class="nav-container" :class="{ 'collapsed': isCollapsed }">
      <ul class="nav-list" >
        <li v-for="(item, index) in navItems" :key="item.id" class="nav-item">
          <a :class="{ 'active': item.isActive }" @click="handleNavClick(index)">{{ item.text }}</a>  
        </li>
      </ul>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
.sidebar {
  width: $sidebar-width;
  flex-shrink: 0;
  background-color: $white;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  
  .logo {
    width: $logo-size;
    height: $logo-size;
    z-index: 100;
    position: absolute;
    top: $sidebar-top-padding + 15px;
    left: $sidebar-width;
    transform: translate(-50%, -50%);
  }

  .hamburger-container {
    display: none;
    z-index: 2;
  }

  .title {
    font-weight: bold;
    padding-top: $sidebar-top-padding;
    padding-bottom: 75px;
    font-weight: 700;
    font-size: 30px;
    line-height: 100%;
    letter-spacing: 0%;
    position: relative;
    z-index: 1;
    background-color: $white;
    
    .title-bird {
      position: absolute;
      bottom: 0;
      left: 0;
    }
  }

  .nav-container {
    flex-grow: 1;
    background-color: #fff;
    width: 100%;
    overflow: hidden;
    max-height: 500px;
    transition: max-height 0.5s ease-in-out;
    .nav-list {
      list-style: none;
      padding: 0;
      margin: 0;
      .nav-item {
        display: flex;
        justify-content: center;
        a {
          width: fit-content;
          text-decoration: none;
          color: $text-color;
          display: block;
          transition: color 0.3s;
          font-weight: 400;
          font-size: 18px;
          line-height: 100%;
          letter-spacing: 0%;
          text-align: center;
          margin-bottom: 21px;
          cursor: pointer;
          
          &.active, &:hover {
            color: $primary-color;
            border-bottom: 2px solid $primary-color;
          }
        }
      }

    }
    &.collapsed {
      @media (max-width: $mobile-breakpoint) {
        max-height: 0;
      }
    }
  }
}

@media (max-width: $mobile-breakpoint) {
  .sidebar {
    width: 100%;
    height: auto;
    position: sticky;
    top: 0;
    left: 0;
    z-index: 1000;
    background-color: rgb(255, 255, 255);
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    display: flex;
    flex-direction: column;

    
    .sidebar-header {
      width: 100%;
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: space-between;
      .hamburger-container {
        display: block;
        padding-left: 26px;
      }
      
      .logo {
        width: $mobile-logo-size;
        height: $mobile-logo-size;
        position:static;
        transform: translateY(0%);
        transform: translateX(0%);
        padding-right: 18px;
      }

      .title {
        padding-top: 30px;
        padding-bottom: 35px;
        font-size: 20px;
      }

    }
    
    .nav-container {
      width: 100%;
      .nav-list {
        padding-bottom: 45px;
      }
      &.collapsed {
        max-height: 0;
        padding-bottom: 0;
      }
    }
  }
  
  body {
    padding-top: 100px;
  }
}
</style>

