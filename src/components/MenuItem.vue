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
    <img class="mitem__img" :src="imgpath" />
    <div class="mitem__content">
      <div class="mitem__content-data">
        <div class="mitem__content-data__headline">
          <h3>{{ name }}</h3>
          <p class="style-h3">{{ price }}</p>
        </div>
        <p class="mitem__content-data__desc">{{ desc }}</p>
      </div>
      <div class="mitem__content-ctrl">
        <div class="mitem__content-ctrl__qty">
          <p>QTY: <span>1</span></p>
        </div>
        <button class="mitem__content-ctrl__btn">Order</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.mitem {
  --height: 9rem;
  --imgspace: calc(100vw - var(--padding-inline) - 22rem);
  --imgcol: clamp(0rem, var(--imgspace), var(--height) + 0.618em);

  display: grid;
  grid-template-columns: var(--imgcol) 1fr;
  max-width: var(--max-width-mitem);
}

.mitem__img {
  object-fit: contain;
  object-position: center;
  height: var(--height);
  width: var(--height);
}

.mitem__content {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  backdrop-filter: blur(0.15rem);
  background-color: #14141480;
  border-inline-start: 4px solid var(--clr-primary);
  padding-inline-start: 0.618em;
}

.mitem__content-data {
  text-shadow: 2px 2px 1px var(--clr-black);
}

.mitem__content-data__headline {
  display: flex;
  justify-content: space-between;
  margin-bottom: var(--gap-s);
}

.mitem__content-data__desc {
  color: var(--clr-white-soft);
  height: 2.25em; /* precisely enough to seamlessly allow 0 or 1 line breaks */
  line-height: 1.25;
  margin-bottom: var(--gap-l);
}

.mitem__content-ctrl {
  display: flex;
}

.mitem__content-ctrl__qty {
  border-start-start-radius: 100vw;
  border-end-start-radius: 100vw;
  background-color: var(--clr-white);
  color: var(--clr-primary);
  font-size: var(--step-1);
  padding-inline: 1em;
  text-shadow: 1px 1px 1px var(--clr-black);
}

.mitem__ctrl-qty span {
  font-weight: 700;
  padding-inline-start: 0.618em;
  text-decoration: underline;
}

.mitem__content-ctrl__btn {
  background-color: var(--clr-primary);
  border: none;
  border-radius: 0 1em 1em 0;
  /* border-radius: inherit; */
  flex: 1;
  font-size: var(--step-1);
  padding: 4px var(--step-0);
  text-transform: uppercase;
}
</style>
