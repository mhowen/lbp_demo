<script setup lang="ts">
import Header from './components/Header.vue';
import Menu   from './components/Menu.vue';
</script>

<template>
  <div id="lbp">
    <Header />
    <Menu />
    <footer class="footer">
      <p>Footer content!</p>
    </footer>
  </div>
</template>

<style scoped>
#lbp {
  --header-height: 5rem;
  --max-width-mitem: 50rem;
  --padding-inline: clamp(1rem, 5vw, 2rem);
  --content-inline-max: 90rem;
  --padding-inline-min: 2rem;
  --inline-free: calc(100vw - var(--content-inline-max));
  --padding-inline-app: max(var(--padding-inline), calc(0.5 * var(--inline-free)));
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
