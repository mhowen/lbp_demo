<script setup lang="ts">
import MenuItem from './MenuItem.vue';
import OrderSummary from './OrderSummary.vue';

import cb1 from '../assets/cb1.png';
import cb2 from '../assets/cb2.png';
import cs1 from '../assets/cs1.png';
import cs2 from '../assets/cs2.png';
import fries from '../assets/fries.png';
import rings from '../assets/rings.png';

const sandwiches = [
  {
    name: "The Classic",
    price: "$9.95",
    desc: "Brioche Bun / All-Beef Patty / American Cheese / LTO / House Mayo",
    imgpath: cb1,
  },
  {
    name: "The Breakfast",
    price: "$10.95",
    desc: "Brioche Bun / All-Beef Patty / Fried Egg / American Cheese / LTO",
    imgpath: cb2,
  },
  {
    name: "The Chicken",
    price: "$9.95",
    desc: "Potato Bun / Fried Chicken Breast / Coleslaw / House Mayo",
    imgpath: cs1,
  },
  {
    name: "The Joseon",
    price: "$10.95",
    desc: "Brioche Bun / Korean Fried Chicken / Slaw / House Mayo",
    imgpath: cs2,
  },
];

const sides = [
  {
    name: "The Fries",
    price: "$6.95",
    desc: "Triple-Cooked Idaho Russets / Garlic / Parmesan / Sea Salt",
    imgpath: fries,
  },
  {
    name: "The Rings",
    price: "$8.95",
    desc: "Georgia-Grown Vidalia Onion Rings / House Mayo",
    imgpath: rings,
  },
];
</script>

<template>
  <div class="page">
    <h1 class="ff-deco mb-l">Our Menu</h1>
    <h2 class="mb-l">Burgers & Sandwiches</h2>
    <div class="menu-list">
      <MenuItem
        v-for="i in sandwiches"
        :key="i.name"
        :name="i.name"
        :price="i.price"
        :desc="i.desc"
        :imgpath="i.imgpath"
      />
    </div>
    <h2 class="mb-l">Fries & Sides</h2>
    <div class="menu-list">
      <MenuItem
        v-for="i in sides"
        :key="i.name"
        :name="i.name"
        :price="i.price"
        :desc="i.desc"
        :imgpath="i.imgpath"
      />
    </div>

    <OrderSummary />
  </div>
</template>

<style scoped>
.page {
  background-color: var(--clr-black);
  padding-inline: var(--padding-inline-app);
  padding-block: var(--gap-xl);
}
.menu-list > * {
  margin-bottom: min(5vh, var(--gap-xl));
}

.mb-l {
  margin-bottom: min(5vh, var(--gap-l));
}

h1,
h2 {
  line-height: 1.00;
  text-shadow: 0.0625em 0.0625em 0.03125em var(--clr-primary);
}
h2 {
  text-decoration: underline 2px;
}
</style>

