<script setup>
const props = defineProps({
  name: {
    type: String,
    required: true,
  },
  price: {
    type: String,
    required: true,
  },
  desc: {
    type: String,
    required: true,
  },
  imgpath: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="mitem">
    <img class="mitem__img pattern" :src="imgpath" />
    <div class="mitem__content">
      <h3 class="mitem__content-headline">{{ name }}</h3>
      <p class="mitem__content-price align-end style-h3">{{ price }}</p>
      <p class="mitem__content-desc">{{ desc }}</p>
      <div class="mitem__content-ctrl">
        <button class="btn btn__fill">-</button>
        <span class="label__qty">1</span>
        <button class="btn btn__fill">+</button>
        <button class="btn btn__fill">Order</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.mitem {
  --height: 9rem;
  --imgspace: calc(100vw - var(--padding-inline) - 22rem);
  --imgcol: clamp(0rem, var(--imgspace), var(--height) + var(--gap-m));

  display: grid;
  grid-template-columns: var(--imgcol) 1fr;
  max-width: var(--max-width-mitem);
}
.mitem__img {
  object-fit: contain;
  object-position: center;
  height: 100%;
  width: var(--height);
}
.mitem__content {
  display: grid;
  grid-template-columns: auto min-content;
  grid-template-rows: auto 1fr auto;
  min-height: var(--height);

  backdrop-filter: blur(0.15rem);
  background-color: var(--clr-black-50);
  border-inline-start: 4px solid var(--clr-primary);
  padding-inline-start: var(--gap-m);
  text-shadow: 2px 2px 1px var(--clr-black);
}
.mitem__content-desc {
  grid-column: span 2;
  color: var(--clr-white-soft);
  line-height: 1.25;
  padding-top: var(--gap-xs);
}
.mitem__content-ctrl {
  grid-column: span 2;
  display: flex;
  align-items: center;
  font-size: var(--step-1);
}
.mitem__content-ctrl > button:last-of-type {
  flex-grow: 1;
  margin-inline-start: var(--gap-s);
}
.label__qty {
  margin-inline: var(--gap-s);
  text-shadow: 2px 2px 2px var(--clr-black);
}
</style>

