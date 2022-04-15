<template>
  <div class="header">
    <the-navbar></the-navbar>
    <div>
      <router-link to="/"
        ><img src="../assets/img/newlogo.svg" alt="logo" class="logo__img"
      /></router-link>
    </div>
    <div class="navbar" v-if="IsLogged">
      <div @click="openHeader()" class="cartCont">
        <img src="../assets/img/cartImg.png" alt="" style="width: 2.08vw" />
        <div class="cartCounter">
          {{ cartSum }}
        </div>
      </div>
      <div class="walletCont">
        <img
          class="walletImg"
          src="../assets/img/walletsvg.svg"
          alt=""
          style="width: 1.25vw"
        />
        <div class="purse__count">0 ₸</div>
        <div class="popolnit" @click="topupMoney">+ пополнить</div>
      </div>
      <div class="user">
        <img
          src="../assets/img/avatarn.svg"
          alt=""
          style="width: 3.75vw"
          class="accountHeaderImgPC"
        />
        <div class="dropdown">
          <img
            src="../assets/img/avatarn.svg"
            alt=""
            style=""
            class="accountHeaderImgM"
          />
          <div class="prodileCont">
            <div class="name">{{ USER_NAME }}</div>
          </div>

          <div class="dropdown-content">
            <a href="/account">Профиль</a>
            <a @click="logOut">Выйти</a>
          </div>
        </div>
      </div>
    </div>
    <div class="sign__in" v-else>
      <button class="signin" data-toggle="modal" data-target="#LogReg">
        Войти
      </button>
      <form action="https://steamcommunity.com/openid/login" method="post">
        <input
          type="hidden"
          name="openid.identity"
          value="http://specs.openid.net/auth/2.0/identifier_select"
        />
        <input
          type="hidden"
          name="openid.claimed_id"
          value="http://specs.openid.net/auth/2.0/identifier_select"
        />
        <input
          type="hidden"
          name="openid.ns"
          value="http://specs.openid.net/auth/2.0"
        />
        <input type="hidden" name="openid.mode" value="checkid_setup" />
        <input
          type="hidden"
          name="openid.realm"
          value="https://bestcases.kz/"
        />
        <input
          type="hidden"
          name="openid.return_to"
          value="https://bestcases.kz/error"
        />
        <button class="signin__steam">
          <img src="../assets/img/steamLog.png" alt="" class="steam__img" />
          <div class="steam__text">Войти через Steam</div>
        </button>
      </form>
    </div>
  </div>
  <cart-menu> </cart-menu>
</template>

<script>
import CartMenu from "../views/CartMenu.vue";
import { mapGetters, mapActions } from "vuex";

export default {
  data() {
    return {};
  },
  components: {
    CartMenu,
  },

  methods: {
    ...mapActions(["LogOut"]),
    logOut() {
      localStorage.setItem("userName", "");
      localStorage.setItem("userEmail", "");
      localStorage.setItem("userLoged", "");
      this.LogOut();
    },
    openHeader() {
      let sc = $("#cart")[0];
      sc.style.transition = "all 0.8s";
      sc.style.display = "block";
      sc.style.right = 0;
      sc.style.top = 0;
    },
    topupMoney() {
      $("#Money").modal("show");
    },
  },
  mounted() {
    let header = document.querySelector(".header");
    window.addEventListener("scroll", function () {
      if (window.scrollY > 50) {
        header.style.backgroundColor = "rgba(255, 255, 255, 0.1)";
        // header.style.paddingTop = '1vw';
        // header.style.paddingBottom = '0.1vw';
      } else {
        header.style.backgroundColor = "";
      }
      // console.log(this.CART_PLS.length)
    });
  },
  computed: {
    ...mapGetters(["CART_PLS", "USER_NAME"]),
    cartSum() {
      return this.CART_PLS.length;
    },
  },
};
</script>

<style scoped>
.popolnit {
  position: absolute;
  bottom: 0.5vw;
  font-size: 0.83vw;
  font-weight: 300;
  color: #ffff;
  cursor: pointer;
}
.cartCont {
  margin-right: 2.6vw;
  cursor: pointer;
  position: relative;
}
.cartCont img {
  width: 40px;
}
.cartCounter {
  color: white;
  position: absolute;
  top: -10px;
  right: -10px;
  background: #f15a24;
  padding: 2px 8px;
  border-radius: 10px;
  font-size: 16px;
}

.accountHeaderImgPC {
}
.prodileCont {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-left: 16px;
}
.walletCont {
  margin-top: -0.5vw;
  margin-right: 2.76vw;
  display: flex;
  align-items: center;
}
.walletImg {
  width: 24px;
}
.steam__img {
  width: 1.25vw;
}

.plusik {
  position: absolute;
  top: 0.36vw;
  left: 3.18vw;
}
.user p {
  margin-bottom: 0 !important;
}
.navbar {
  align-items: center;
}
.dropdown {
  position: relative;
  display: inline-block;
  text-align: center;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #332e24;;
  /* min-width: 160px; */
  box-shadow: 0px 8px 8px 0px rgb(234 196 139 / 20%);
  z-index: 1;
}

.dropdown-content a {
  color: #fff;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  cursor: pointer;
}

.dropdown-content a:hover {
  background-color: #EAC48B;
  color: white;
}

.dropdown:hover .dropdown-content {
  display: block;
}

/* .dropdown:hover .name {
  background-color: #3e8e41;
} */
.steam__text {
  font-weight: 500;
  font-size: 1.042vw;
  text-align: center;
  color: #fff;
  padding-left: 0.52vw;
}
.sign__in {
  display: flex;
  align-items: center;
}
.signin {
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24;
  box-sizing: border-box;
  border-radius: 5px;
  color: #fff;
  font-weight: 500;
  font-size: 1.042vw;
  padding: 0.5vw 1.41vw 0.5vw 1.41vw;
  margin-right: 2.24vw;
}
.signin__steam {
  display: flex;
  align-items: center;
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24;
  box-sizing: border-box;
  border-radius: 5px;
  padding: 0.5vw 1.41vw 0.5vw 1.41vw;
  font-weight: 500;
  /* height: 3.54vw; */
}
.header {
  background: rgba(255, 255, 255, 0.1);
  width: 100%;
  z-index: 5;
  position: fixed;
  padding-top: 0.5vw;
  padding-left: 2.6vw;
  padding-right: 1.35vw;
  padding-bottom: 0.5vw;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.logo__img {
  width: 7.81vw;
}
.navbar__btn:hover {
  background: linear-gradient(235.92deg, #753ef9 14.85%, #9d75ff 87.62%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.purse {
  position: relative;
  display: flex;
}
.purse__btn {
  display: flex;
  border: 0;
  background: linear-gradient(83.8deg, #c62c44 15.62%, #ff0027 91.62%);
  border-radius: 10px;
  width: 4.01vw;
  height: 2.24vw;
}
.purse__count {
  font-weight: 500;
  font-size: 1.46vw;
  color: #fff;
  margin-left: 16px;
}

.name {
  cursor: pointer;
  color: #fff;
  font-weight: 400;
  font-size: 1.146vw;
  /* padding-left: 0.68vw; */
  /* padding-right: 0.68vw; */
}
.user {
  display: flex;
  margin-left: 1.823vw;
  margin-right: 0.78vw;
  align-items: center;
}
.cart__btn {
  padding: 0.1vw 0.73vw 0.78vw 0.73vw;
  height: 2.24vw;
  background: linear-gradient(83.8deg, #c62c44 15.62%, #ff0027 91.62%);
  border-radius: 10px;
  border: 0;
  display: flex;
}
.cart__count {
  font-weight: 500;
  font-size: 1.46vw;
  color: #fff;
  padding-left: 7px;
}
@media screen and (min-width: 481px) {
  .accountHeaderImgM {
    display: none;
  }
}
@media screen and (max-width: 480px) {
  .purse__count {
    font-size: 2.55vw;
  }
  .walletCont {
    display: none;
    padding-right: 5vw;
  }
  .walletImg {
    width: 3vw !important;
  }
  .cartCounter {
    font-size: 1.55vw;
  }
  .cartCont img {
    width: 4vw !important;
  }
  .header {
    position: fixed;
    align-items: center;
    background-color: rgb(32, 32, 37);
  }
  .signin__steam {
    display: none;
  }
  .logo__img {
    width: 14.26vw;
  }
  .signin {
    font-size: 3vw;
    height: unset;
  }
  .purse {
    display: none;
  }
  .user {
    /* flex-direction: column; */
    align-items: center;
  }
  .name {
    /* margin-bottom: 0;
    font-size:12px; */
    display: none;
  }
  .navbar {
    padding: 0.5rem 0.5rem;
  }
  .accountHeaderImgPC {
    display: none;
  }
  .accountHeaderImgM {
    width: 7vw;
  }
  .cart__btn {
    width: 9vw;
    height: 6vw;
    align-items: center;
    padding: 0;
    justify-content: center;
    margin-left: 10px;
  }
  .cart__btn img {
    padding-top: 0 !important;
    width: 3vw !important;
  }
  .cart__count {
    margin-bottom: 0;
    display: none;
  }
  .dropdown-content {
    min-width: unset;
  }
  .dropdown-content a {
    padding: 5px 5px;
  }
}
</style>