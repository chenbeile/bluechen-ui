<template>
<div class="topnav">
  <div class="logo">LOGO</div>
  <ul class="menu">
    <li>菜单1</li>
    <li>菜单2</li>
  </ul>
  <span class="toggleAside" @click="toggleMenu"></span>
</div>
</template>

<script lang="ts">
import {
  inject,
  Ref
} from 'vue'
export default {
  setup() {
    const asideVisible = inject < Ref < boolean > > ('asideVisible')
    const toggleMenu = () => {
      asideVisible.value = !asideVisible.value
    }
    return {
      toggleMenu
    }
  }
}
</script>

<style lang="scss" scoped>
.topnav {
  background: pink;
  display: flex;
  padding: 16px;
  position: relative;
  z-index: 10;
  justify-content: center;
  align-items: center;

  >.logo {
    max-width: 6rem;
    margin-right: auto;
  }

  >.menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;

    >li {
      margin: 0 1em;
    }
  }

  >.toggleAside {
    display: inline-block;
    width: 24px;
    height: 24px;
    background: red;
    position: absolute;
    left: 16px;
    top: 50%;
    transform: translateY(-50%);
    display: none;
  }

  @media (max-width: 500px) {
    >.menu {
      // 小于500px隐藏menu菜单
      display: none;
    }

    >.logo {
      margin: 0 auto;
    }

    >.toggleAside {
      display: inline-block;
    }
  }
}
</style>
