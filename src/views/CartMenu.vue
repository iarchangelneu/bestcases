<template>
  <div class="cart" id="cart">
    <div class="cart_container">
      <div class="cart__content">
        <img
          src="../assets/img/close.svg"
          alt=""
          @click="closeHeader()"
          style="cursor: pointer; width: 3.65vw"
        />
        <p class="your__cart">Ваша корзина</p>
      </div>
      <CartItemMenu :cart_data="CART_PLS"></CartItemMenu>
      <hr style="width: 29.74vw" />
      <div class="cart__total pl__pr">
        <p class="cart__total__text">Итого</p>
        <p class="cart__total__text">{{ cartSum + "₸" }}</p>
      </div>
      <div class="cart__buttons pl__pr">
        <router-link to="cart"
          ><a class="cart__src">Перейти в корзину</a></router-link
        >
        <button
          class="cart__button"
          data-toggle="modal"
          data-target="#exampleModal"
        >
          Оформить заказ
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import CartItemMenu from "../views/CartItemMenu.vue";
import { mapGetters } from "vuex";

export default {
  data() {
    return {};
  },
  components: {
    CartItemMenu,
  },
  props: {
    cart_item_data: {
      type: Object,
      default() {
        return [];
      },
    },
  },
  methods: {
    closeHeader() {
      let sc = $("#cart")[0];
      sc.style.transition = "all 0.8s";
      sc.style.right = -101 + "vw";
    },
    deleteCart() {
      this.$emit("deleteCart");
    },
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
};
</script>

<style>
.your__cart {
  font-weight: 500;
  font-size: 1.67vw;
  color: #ffffff;
  text-align: center;
  margin-left: 7vw;
}
.test::-webkit-scrollbar {
  background: #181820;
  border-radius: 15px;
  width: 9px;
}
.test::-webkit-scrollbar-thumb {
  border-radius: 15px;
  background-color: #f15a24;
}
.test::-webkit-scrollbar-track {
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.2);
  border-radius: 15px;
  background-color: #181820;
}
.test {
  height: 500px;
  overflow-y: scroll;
}
.cart__button {
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24;
  box-sizing: border-box;
  border-radius: 5px;
  padding: 0.83vw 6.93vw 0.83vw 6.93vw;
  text-transform: uppercase;
  color: #fff;
  font-weight: 500;
  font-size: 1.04vw;
  border: 0;
  margin-bottom: 1.67vw;
}
.cart__total__text {
  font-weight: 500;
  font-size: 1.46vw;
  color: #fff;
}
.cart__src {
  font-weight: 400;
  font-size: 1.04vw;
  text-decoration-line: underline;
  color: #fff;
}
.cart__total {
  margin-top: 2.08vw;
  display: flex;
  justify-content: space-between;
}
.cart__buttons {
  margin-top: 2.45vw;
  text-align: center;
  display: flex;
  flex-direction: column-reverse;
}
hr {
  border: 1px solid #f7f7f7;
}
.product__price {
  margin-top: 5.63vw;
}
.product__count {
  font-weight: 400;
  font-size: 1.25vw;
  color: #f7f7f7;
  margin-right: 3vw;
  white-space: nowrap;
}
.product__text {
  font-weight: 500;
  font-size: 0.83vw;
  color: #f7f7f7;
}
.product__name {
  font-weight: 400;
  font-size: 1.25vw;
  color: #fff;
}
.product__close {
  position: absolute;
  left: 26.08vw;
  top: 0;
}
.cart__products {
  margin-top: 3.96vw;
  margin-bottom: 2.4vw;
}
.cart__product {
  background: transparent;
  border-radius: 0.26vw;
  display: flex;
  position: relative;
  justify-content: space-around;
  align-items: center;
}
.pl__pr {
  padding-left: 2.08vw;
  padding-right: 2.08vw;
}
.cart__content {
  padding-top: 2.6vw;
  padding-left: 1.2vw;
  padding-right: 1.56vw;
  display: flex;
  align-items: center;
}
.cart__summary {
  display: flex;
  font-weight: 500;
  font-size: 1.46vw;
  color: #f7f7f7;
  background: linear-gradient(83.8deg, #c62c44 15.62%, #ff0027 91.62%);
  border-radius: 0.26vw;
  padding: 0.26vw 0.26vw 0.26vw 0.26vw;
  align-items: center;
}
.cart {
  height: 100vh;
  width: 33.85vw;
  display: block;
  /*height: 100%;*/
  transition: all 2.2s ease 0s;
  right: -101vw;
  top: 0px;
  position: fixed;
  background-color: white;
  z-index: 1001;
  overflow: auto;
  background: #1a1814;
  box-shadow: -10px 0px 15px rgba(0, 0, 0, 0.15);

}
.cart__productIMG {
  background: rgba(48, 47, 56, 0.5);
  box-shadow: 2px 4px 10px rgba(0, 0, 0, 0.25);
  border-radius: 0.99vw;
}
@media screen and (max-width: 480px) {
  .cart {
    width: 90vw;
  }
  .cart__productIMG {
    width: 23vw !important;
  }
  .product__name {
    font-size: 14px;
    margin-bottom: 0.5rem;
  }
  .product__text {
    font-size: 12px;
    margin-bottom: 0.5rem;
  }
  .product__count {
    font-size: 12px;
  }
  .product__close {
    left: unset;
    right: 10px;
  }
  .product__close img {
    width: 5vw !important;
  }
  .cart__total__text {
    font-size: 14px;
  }
  .cart__src {
    font-size: 14px;
  }
  .cart__button {
    font-size: 14px;
  }
  .cart_container {
    padding-bottom: 30px;
  }
  .test {
    height: 400px;
  }
  .cart__content img {
    width: 8vw !important;
  }
  .cart__summary {
    font-size: 14px;
    margin-bottom: 0;
  }
  .cart__summary img {
    width: 5vw !important;
  }
}
</style>