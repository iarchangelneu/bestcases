<template>
  <div class="lc__title">
    <img src="@/assets/img/cartlc.svg" style="width: 20.83vw" alt="" />
  </div>
  <div class="cart__page pl__pr">
    <div class="cart__pagecontent p__content">
      <cart-item-page :cart_data="CART_PLS"></cart-item-page>
      <hr />
      <div class="product__summary">
        <p style="margin-right: 7.55vw">Итого</p>
        <p>{{ cartSum }} ₸</p>
      </div>
      <div class="total">
        <div>
          <button class="buy__btn" @click="tryToBuy">
            Перейти к оформлению
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import CartItemPage from "../views/CartItemPage.vue";
export default {
  props: {
    cart_item_data: {
      type: Object,
      default() {
        return [];
      },
    },
  },
  data() {
    return {
      showModal: false,
      productTotal: 1,
    };
  },
  components: {
    CartItemPage,
  },
  computed: {
    ...mapGetters(["CART_PLS"]),
    cartSum() {
      console.log(this.CART_PLS);
      return this.CART_PLS.reduce(
        (previousValue, currentValue) =>
          previousValue + Math.floor(currentValue.cost),
        0
      );
    },
  },
  methodsdeleteCart() {
    this.$emit("deleteCart");
  },
};
</script>

<style scoped>
.lc__title {
  padding-top: 10vw;
  display: flex;
  justify-content: center;
}
.buy__btn {
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24;
  box-sizing: border-box;
  border-radius: 5px;
  padding: 0.83vw 2.6vw 0.83vw 2.6vw;
  font-weight: 400;
  font-size: 1.04vw;
  color: #fff;
  border: 0;
}
.product__summary {
  display: flex;
  font-weight: 500;
  font-size: 2.08vw;
  color: #fff;
  justify-content: flex-end;
}
.total {
  display: flex;
  justify-content: flex-end;
}
.product__close {
  top: 0;
  left: 79.69vw;
}
.product__total {
  font-weight: 600;
  font-size: 2.08vw;
  color: #f7f7f7;
}
.right {
  border-left: 3px solid #f7f7f7 !important;
}
.left {
  border-right: 3px solid #f7f7f7 !important;
}
.product__sumbtn {
  border: 0;
  background: transparent;
  color: #fff;
  font-size: 1.67vw;
}
.product__sum {
  font-weight: 600;
  font-size: 2.08vw;
  color: #ffffff;
  padding-left: 1.72vw;
  padding-right: 1.72vw;
}
.product__countbtns {
  border: 3px solid #f7f7f7;
  box-sizing: border-box;
  border-radius: 5px;
  width: 11.46vw;
  height: 3.02vw;
  display: flex;
}
.product__content {
  position: relative;
  display: flex;
  background: #36353c;
  border-radius: 5px;
  align-items: center;
  justify-content: space-around;
  margin-right: 1.04vw;
  margin-bottom: 2.71vw;
}
.cart__main {
  text-align: center;
  color: #fff;
  font-weight: 800;
  font-size: 3.13vw;
  letter-spacing: 0.025em;
  padding-bottom: 4vw;
}
.cart__page {
  padding-top: 4.54vw;
  margin-bottom: 6.41vw;
}
.cart__pagecontent {
  border: 1px solid rgba(234, 196, 139, 0.5);
  box-sizing: border-box;
  border-radius: 5px;
  border-radius: 0.78vw;
}
.pl__pr {
  padding-left: 1.77vw;
  padding-right: 1.77vw;
}
.p__content {
  padding-top: 2.76vw;
  padding-bottom: 2.76vw;
  padding-left: 5.21vw;
  padding-right: 5.21vw;
}
.product__sumbtn img {
  width: 100%;
}
@media screen and (max-width: 480px) {
  .product__total {
    font-size: 12px;
  }
  .product__summary {
    font-size: 16px;
  }
  .buy__btn {
    font-size: 14px;
  }
}
</style>