<script setup lang="ts">
import { ref } from 'vue';

const navtray_open = ref(false);
</script>

<template>
  <header class="header">
    <div class="header__logo">LBP</div>
    <nav class="header__nav" :class="{ opened: navtray_open }">
      <a class="active">Menu</a>
      <a>Locations</a>
      <a>Merchandise</a>
      <a>Order Online</a>
    </nav>
    <svg class="header__hamburger" @click="navtray_open = !navtray_open"
      xmlns="http://www.w3.org/2000/svg" width="3.5em" height="3.5em" viewBox="0 0 24 24">
      <g fill="none" stroke="currentColor" stroke-linecap="round" stroke-width="1.5">
        <path d="M20 7H4"/>
        <path d="M20 12H4" opacity="0.5"/>
        <path d="M20 17H4"/></g>
    </svg>
  </header>
</template>

<style scoped>
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: var(--header-height);
  overflow-x: hidden;
  position: sticky;
  top: 0;
  z-index: 999;

  background-color: var(--clr-primary);
  border-bottom: 0.25em solid var(--clr-primary-mute);
  padding-inline: var(--padding-inline-app);
}
.header__logo {
  cursor: pointer;
  font-family: Lobster, Oswald, Inter;
  font-size: 2.75rem;
  line-height: 1.25; /* makes centering goofy Lobster font easier */
  user-select: none;
}
.header__nav {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: var(--step-3);
  position: fixed;
  inset: 0;

  backdrop-filter: blur(0.25rem);
  background-color: #8a221ce0;
  font-family: Oswald, Inter;
  font-size: calc(var(--step-1) * var(--halfstep));
  text-transform: uppercase;
  transform: translateX(100%);
  transition: transform 250ms ease-in;
  z-index: -1;
}
.header__nav.opened {
  transform: translateX(0%);
}
.header__nav > a {
  color: var(--clr-white-soft);
  user-select: none;
  transition: color 150ms ease-in;
}
.header__nav > a:hover {
  color: var(--clr-white);
  cursor: pointer;
}
.header__nav > a.active {
  color: var(--clr-white);
  text-decoration: underline;
}

@media (min-width: 72.5rem) {
  .header__nav {
    flex-direction: row;
    position: static;
    transform: translateX(0%);
  }
  .header__hamburger { display: none; }
}
</style>

