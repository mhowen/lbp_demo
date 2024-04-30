<script setup lang="ts">
import Header from './components/Header.vue';
import Menu   from './components/Menu.vue';
</script>

<template>
  <div id="lbp">
    <Header />
    <Menu />
    <footer class="footer">
      <p class="align-center">
      ©2024 M. Harrison Owen --
      <a href="https://www.mharryowen.com">www.mharryowen.com</a>
      </p>
    </footer>
  </div>
</template>

<style>
#lbp {
  display: flex;
  flex-direction: column;
  min-height: 100%;
}
.page {
  flex: 1;
}
.footer {
  border-top: 1px solid var(--clr-white);
}
</style>

