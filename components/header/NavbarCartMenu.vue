<template>
  <div class="cart-menu-inner">
    <div class="top">
      <div class="top-header">
        <h3 class="body-xl-500">Shopping Cart (2)</h3>
        <button @click="closeCartMenu">&times;</button>
      </div>
      <div class="top-product">
        <img src="/assets/images/cart-menu/product-1.png" alt="Oranges" />
        <div class="top-product-text body-sm-400">
          <div class="name">Fresh Indian Orange</div>
          <div class="total">
            <span class="quantity">1 kg</span>
            <span>&times;</span>
            <span class="price">12.00</span>
          </div>
        </div>
        <button>&times;</button>
      </div>
      <div class="top-divider"></div>
      <div class="top-product">
        <img src="/assets/images/cart-menu/product-2.png" alt="Apples" />
        <div class="top-product-text body-sm-400">
          <div class="name">Green Apple</div>
          <div class="total">
            <span class="quantity">1 kg</span>
            <span>&times;</span>
            <span class="price">14.00</span>
          </div>
        </div>
        <button>&times;</button>
      </div>
    </div>
    <div class="bottom">
      <div class="bottom-header">
        <span class="body-md-400"> 2 products </span>
        <span class="body-md-600"> $26.00 </span>
      </div>
      <div class="buttons">
        <Button label="Checkout" size="large" />
        <Button label="Go To Cart" type="ghost" size="large" />
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps(["closeCartMenu"]);
</script>

<style scoped>
.cart-menu-inner {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  padding: 40px;
  justify-content: space-between;

  .top {
    display: flex;
    flex-direction: column;
    gap: 12px;

    .top-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      button {
        font-size: 28px;
        line-height: 1;
      }
    }
    .top-divider {
      height: 1px;
      background-color: var(--gray-100);
    }
    .top-product {
      display: flex;
      gap: 8px;
      align-items: center;
      img {
        width: 120px;
      }
      .top-product-text {
        flex-grow: 1;
        .name {
        }
        .total {
          display: flex;
          align-items: center;
          gap: 4px;
          color: var(--gray-500);
          .price {
            color: var(--gray-900);
            font-weight: 600;
          }
        }
      }
      button {
        width: 24px;
        height: 24px;
        border-radius: 50%;
        border: 1px solid var(--gray-200);
        line-height: 1;
        display: grid;
        place-items: center;
        font-size: 20px;
        padding: 0;
        color: var(--gray-600);
        transition: 0.3s ease;
        &:hover {
          border-color: var(--gray-900);
          color: var(--gray-900);
        }
      }
    }
  }

  .bottom {
    display: flex;
    flex-direction: column;
    .bottom-header {
      display: flex;
      justify-content: space-between;
      padding: 24px 0;
    }
    .buttons {
      display: flex;
      flex-direction: column;
      gap: 12px;
    }
  }
}
</style>
