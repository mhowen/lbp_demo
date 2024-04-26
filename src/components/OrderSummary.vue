<script setup>

</script>

<template>
  <div class="wrapper">
    <div class="summary__mobile">
      <p>🛒 (2)</p>
      <p>Subtotal: <span>$20.90</span></p>
    </div>
    <div class="summary">
      <h3 class="summary__heading">Your Order</h3>
      <div class="summary__data">
        <h4 class="summary__data-label">Qty</h4>
        <ul class="summary__data-list">
          <li>1</li>
          <li>1</li>
        </ul>
      </div>
      <div class="summary__data">
        <h4 class="summary__data-label">Item</h4>
        <ul class="summary__data-list">
          <li>Classic</li>
          <li>Breakfast</li>
        </ul>
      </div>
      <div class="summary__data">
        <h4 class="summary__data-label">Price</h4>
        <ul class="summary__data-list">
          <li>$9.95</li>
          <li>$10.95</li>
        </ul>
      </div>
      <div class="summary__data total">
        <h4 class="summary__data-label">Subtotal</h4>
        <p class="summary__data-price">$20.90</p>
      </div>
      <div class="summary__data total">
        <h4 class="summary__data-label">Tax</h4>
        <p class="summary__data-price">$1.46</p>
      </div>
      <div class="summary__data total">
        <h4 class="summary__data-label">Total</h4>
        <p class="summary__data-price">$22.36</p>
      </div>
      <button class="summary__btn">🛒 Checkout</button>
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

  background-color: var(--clr-white);
  color: var(--clr-black);
  font-size: var(--step-1);
}
.summary__mobile {
  min-height: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-inline: var(--padding-inline);
}
.summary { display: none }

@media (min-width: 80rem) {
  .summary__mobile { display: none }
  .wrapper {
    min-width: initial;
    left: calc(
      var(--padding-inline-app) +
      var(--padding-inline)     +
      var(--max-width-mitem)
    );
    right: var(--padding-inline-app);
    top: calc(var(--header-height) + 4rem);
    height: min(65rem, 100vh - var(--header-height) - 8rem);

    border-inline-start: 4px solid var(--clr-primary);
    border-block-end: 4px solid var(--clr-primary);
    border-radius: 1em;
    text-transform: uppercase;
  }
  .summary {
    font-size: var(--step-0);
    display: grid;
    min-height: 100%;
    gap: var(--gap-s) var(--gap-l);
    grid-template-columns: auto 1fr auto;
    grid-template-rows: auto 1fr auto auto auto;
    padding-inline: var(--padding-inline);
    position: relative;
  }
  /* qty/price */
  .summary > .summary__data:nth-child(2),
  .summary > .summary__data:nth-child(4) {
    text-align: end;
  }

  .summary__heading,
  .summary__data-label {
    color: var(--clr-primary);
    font-size: var(--step-1);
  }
  .summary__heading {
    grid-column: span 3;
    font-family: Lobster, Oswald;
    font-size: var(--step-2);
    margin-block: var(--gap-l) var(--gap-m);
    text-align: center;
    text-decoration: underline 4px;
  }
  .summary__data-list > li {
    border-block-end: 1px solid var(--clr-white-soft);
    margin-block-end: var(--gap-m);
  }
  .summary__data.total {
    grid-column: span 3;
    display: flex;
    align-items: center;
    font-size: var(--step-1);
  }
  .summary__data.total > .summary__data-label {
    flex: 1;
  }
  .summary__data.total:last-of-type {
    font-weight: 700;
    margin-block-end: var(--gap-xxl);
  }
  .summary__btn {
    position: absolute;
    bottom: 0;
    left: 50%;
    min-width: max(20rem, 66%);
    transform: translateX(-50%);

    background-color: var(--clr-primary);
    border: none;
    border-bottom-left-radius: 0;
    border-bottom-right-radius: 0;
    font-size: var(--step-1);
    padding: var(--gap-s) var(--gap-l);
    text-transform: uppercase;
  }
}
</style>

