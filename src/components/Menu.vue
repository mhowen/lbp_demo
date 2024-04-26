<script setup lang="ts">
import MenuItem from './MenuItem.vue';
import OrderSummary from './OrderSummary.vue';

const sandwiches = [
  {
    name: "The Classic",
    price: "$9.95",
    desc: "Brioche Bun / All-Beef Patty / American Cheese / LTO / House Mayo",
    imgpath: "/cb1.png",
  },
  {
    name: "The Breakfast",
    price: "$10.95",
    desc: "Brioche Bun / All-Beef Patty / Fried Egg / American Cheese / LTO",
    imgpath: "/cb2.png",
  },
  {
    name: "The Chicken",
    price: "$9.95",
    desc: "Potato Bun / Fried Chicken Breast / Coleslaw / House Mayo",
    imgpath: "/cs2.png",
  },
  {
    name: "The Joseon",
    price: "$10.95",
    desc: "Brioche Bun / Korean Fried Chicken / Slaw / House Mayo",
    imgpath: "/cs1.png",
  },
];

const sides = [
  {
    name: "The Fries",
    price: "$6.95",
    desc: "Triple-Cooked Idaho Russets / Garlic / Parmesan / Sea Salt",
    imgpath: "/fries.png",
  },
  {
    name: "The Onion Rings",
    price: "$8.95",
    desc: "Georgia-Grown Vidalia Rings / House Mayo",
    imgpath: "/rings.png",
  },
]
</script>

<template>
  <div class="page">
    <h1>Our Menu</h1>
    <h2>Burgers & Sandwiches</h2>
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
    <h2>Fries & Sides</h2>
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
  font-size: var(--step-0);
  padding-inline: var(--padding-inline-app);
  padding-block-start: 2rem;
}
.menu-list > * {
  margin-bottom: var(--gap-xxl);
}

h1,
h2 {
  line-height: 1.00;
  margin-block-end: var(--gap-l);
}
h2 {
  text-decoration: underline 2px;
}
</style>

