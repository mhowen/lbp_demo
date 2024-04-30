<script setup lang="ts">
defineProps({
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
    <img class="mitem__img" :src="imgpath" />
    <div class="mitem__content">
      <div class="flexrow mb-s">
        <h3>{{ name }}</h3>
        <p class="style-h3">{{ price }}</p>
      </div>
      <p class="mitem__content-desc">{{ desc }}</p>
      <div class="mitem__content-ctrl">
        <button class="btn btn__fill bg-checkered">-</button>
        <span class="fs-1">1</span>
        <button class="btn btn__fill bg-checkered">+</button>
        <button class="btn btn__fill ms-s">Order</button>
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
  background-image: var(--tiled);
  border-top-left-radius: 1em;
  object-fit: contain;
  object-position: center;
  height: 100%;
  width: var(--height);
}
.mitem__content {
  display: flex;
  flex-direction: column;
  min-height: var(--height);

  backdrop-filter: blur(0.10rem);
  background-color: var(--clr-black-50);
  border-inline-start: 4px solid var(--clr-primary);
  padding-inline-start: var(--gap-m);
  text-shadow: 2px 2px 1px var(--clr-black);
}
.mitem__content-desc {
  flex-grow: 1;
  color: var(--clr-white-soft);
  line-height: 1.25;
}
.mitem__content-ctrl {
  display: flex;
  align-items: center;
  gap: var(--gap-m);
}
.mitem__content-ctrl > button:last-of-type {
  flex-grow: 1;
}
</style>

