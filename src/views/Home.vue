<template>
<div>
  <Topnav />
  <div class="banner">
    <h1>轱辘ui</h1>
    <h2>一个厉害的ui框架</h2>
    <p class="actions">
      <a href="">github</a>
      <a href="">开始</a>
    </p>
  </div>
</div>
</template>

<script lang="ts">
import Topnav from '../components/Topnav.vue'
export default {
  components: {
    Topnav
  }
}
</script>

<style lang="scss" scoped>
.topnav {
  background: pink;
  display: flex;
  padding: 16px;

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
}
</style>
