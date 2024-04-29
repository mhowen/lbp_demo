<script setup>

</script>

<template>
  <div class="wrapper">
    <div class="summary__mobile">
      <p>🛒 (2)</p>
      <p>Subtotal: <span>$20.90</span></p>
    </div>
    <div class="summary">
      <h3 class="summary__heading align-center clr-primary">Your Order</h3>
      <div class="summary__data">
        <h4 class="summary__data-label">Qty</h4>
        <ul class="summary__data-list align-end">
          <li>1</li>
          <li>1</li>
        </ul>
      </div>
      <div class="summary__data">
        <h4>Item</h4>
        <ul class="summary__data-list">
          <li>Classic</li>
          <li>Breakfast</li>
        </ul>
      </div>
      <div class="summary__data">
        <h4>Price</h4>
        <ul class="summary__data-list align-end">
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
    top: 50%;
    transform: translateY(-50%);
    height: min(48rem, 80vh);

    border-inline-start: 4px solid var(--clr-primary);
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
  .summary h4 {
    color: var(--clr-primary);
    font-size: var(--step-1);
  }
  .summary__heading {
    grid-column: span 3;
    font-family: Lobster, Oswald;
    font-size: var(--step-2);
    margin-block: var(--gap-l) var(--gap-m);
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
    left: -0.25rem;
    min-width: calc(100% + 0.25rem);

    border: none;
    border-radius: 0 0 1em 1em;
    padding-block: var(--gap-s);
  }
}
</style>

