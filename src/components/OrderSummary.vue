<template>
  <div class="wrapper">
    <div class="summary__mobile">
      <p>🛒 (3)</p>
      <p>Subtotal: <span>$34.80</span></p>
    </div>
    <div class="summary">
      <h3 class="heading heading-main align-center ff-deco fs-2 underline">
        Your Order
      </h3>
      <div class="data">
        <div class="pl-std">
          <h4 class="heading heading-col style-h3">Qty</h4>
          <ul class="datalist align-end">
            <li>1</li>
            <li>1</li>
            <li>2</li>
          </ul>
        </div>
        <div class="pi-std">
          <h4 class="heading heading-col style-h3">Item</h4>
          <ul class="datalist">
            <li>Classic</li>
            <li>Breakfast</li>
            <li>Fries</li>
          </ul>
        </div>
        <div class="pr-std">
          <h4 class="heading heading-col style-h3">Price</h4>
          <ul class="datalist align-end">
            <li>$9.95</li>
            <li>$10.95</li>
            <li>$13.90</li>
          </ul>
        </div>
      </div>
      <div class="fs-1 pi-std">
        <div class="flexrow">
          <h4 class="heading heading-row">Subtotal</h4>
          <p>$34.80</p>
        </div>
        <div class="flexrow">
          <h4 class="heading heading-row">Tax</h4>
          <p>$2.44</p>
        </div>
        <div class="flexrow">
          <h4 class="heading heading-row">Total</h4>
          <p class="fw-700">$37.24</p>
        </div>
      </div>
      <button class="btn summary__btn">🛒 Checkout</button>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  position: fixed;
  height: var(--header-height);
  min-width: 100vw;
  left: 0;
  bottom: 0;

  background-color: var(--clr-black);
  background-image: var(--dappled);
  font-size: var(--step-1);
}
.summary__mobile {
  border-top: 0.125em solid var(--clr-primary);
  min-height: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-inline: var(--padding-inline);
}
.summary {
  display: none;
  font-size: var(--step-0);
}

@media (min-width: 80rem) {
  .summary__mobile { display: none }
  .wrapper {
    --block-usable: calc(100vh - var(--header-height));
    --block-offset: calc(-50% + var(--header-height));
    --inline-offset: calc(var(--padding-inline-app) + var(--padding-inline));
    height: min(48rem, 80vh);
    min-width: min-content;
    left: calc(var(--inline-offset) + var(--max-width-mitem));
    right: var(--padding-inline-app);
    top: calc(var(--block-usable) / 2);
    transform: translate(0%, var(--block-offset));

    border-inline-start: 0.0625em solid var(--clr-black-soft);
    border-inline-end: 0.125em solid var(--clr-primary-mute);
    border-radius: 1em;
    text-transform: uppercase;
  }
  .summary {
    min-height: 100%;
    display: flex;
    flex-direction: column;
  }
  .data {
    flex: 1;
    display: grid;
    grid-template-columns: auto 1fr auto;
  }
  .heading { text-shadow: 0.0625em 0.0625em 0.03125em var(--clr-primary); }
  .heading-col { margin-bottom: var(--gap-m); }
  .heading-row { margin-bottom: var(--gap-s); }
  .heading-main { margin-block: var(--gap-xl) var(--gap-l); }
  .datalist > li {
    border-block-end: 1px solid var(--clr-white-soft);
    margin-bottom: var(--gap-s);
  }
  .summary__btn {
    background-image: var(--diagonals);
    border: none;
    border-bottom: 0.125em solid var(--clr-primary-mute);
    border-radius: 0 0 1em 1em;
    padding-block: var(--gap-s);
  }
}
</style>

