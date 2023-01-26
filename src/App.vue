<template>
  <the-header></the-header>
  <router-view />
  <the-footer></the-footer>

  <ops-modal v-if="IsLogged">
    <template #header>
      <div class="modal__header">
        <img src="./assets/img/opswallet.png" alt="" style="width: 5.73vw" />
      </div>
    </template>
    <template #body>
      <div class="modal__body">
        <p class="modal__textOps">Упс... Что-то не так</p>
        <p class="modal__text">
          Произошла ошибка. Для её устранения вам<br />
          необходимо пополнить свой баланс
        </p>
      </div>
    </template>
    <template #footer>
      <div class="modal__btn">
        <button class="modal__button">
          <a class="modal__href" @click="openTopUp()">Пополнить баланс</a>
        </button>
      </div>
    </template>
  </ops-modal>

  <ops-modal v-else>
    <template #header>
      <div class="modal__header">
        <img src="./assets/img/opslogin.png" alt="" style="width: 7.81vw" />
      </div>
    </template>
    <template #body>
      <div class="modal__body">
        <p class="modal__text">Упс... Что-то не так</p>
        <p class="modal__text">
          Произошла ошибка. Для того, чтобы продолжить вам<br />
          необходимо авторизоваться
        </p>
      </div>
    </template>
    <template #footer>
      <div class="modal__btn">
        <button class="modal__button">
          <a class="modal__href" @click="openSignIn()">Войти</a>
        </button>
      </div>
    </template>
  </ops-modal>

  <log-reg>
    <template #header>
      <div class="logreg__main">Авторизация</div>
    </template>
    <template #body>
      <div class="modal__inputs">
        <div>
          <form>
            <div>
              <label for="login" class="modal__label">Логин</label><br />
              <input
                type="text"
                name="loggin"
                id="loggin"
                class="modal__input"
                placeholder="Введите Логин"
                v-model="username"
              />
            </div>

            <div>
              <label for="password" class="modal__label">Пароль</label><br />
              <input
                type="password"
                name="password"
                id="password"
                class="modal__input"
                placeholder="Введите пароль"
                v-model="password"
              />
            </div>
          </form>
        </div>
      </div>
      <div class="modal__btn">
        <button class="modal__signin" @click="login">Войти</button>
      </div>
    </template>
    <template #footer>
      <div class="modal__haveacc">
        <div class="not__acc">
          <p class="haveacc__main">Нет аккаунта?</p>
          <a class="haveacc__href" @click="openReg()">Зарегистрироваться</a>
        </div>
        <div class="haveacc__btn">
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
            <button class="haveacc__button">
              <img
                src="./assets/img/steamico.svg"
                alt=""
                style="width: 1.25vw; margin-right: 0.52vw"
              />Войти через Steam
            </button>
          </form>
        </div>
      </div>
    </template>
  </log-reg>

  <reg-modal>
    <template #header>
      <div class="logreg__main">Регистрация</div>
    </template>
    <template #body>
      <div class="modal__inputs">
        <div>
          <div>
            <label for="email" class="modal__label">E-mail</label><br />
            <input
              type="email"
              name="email"
              id="email"
              class="modal__input"
              placeholder="Введите e-mail"
              v-model="emailR"
            />
          </div>

          <div>
            <label for="login" class="modal__label">Логин</label><br />
            <input
              type="text"
              name="login"
              id="login"
              class="modal__input"
              placeholder="Введите логин"
              v-model="usernameR"
            />
          </div>

          <div>
            <label for="repeat-password" class="modal__label">Введите пароль</label
            ><br />
            <input
              type="password"
              name="repeat-password"
              id="repeat-password"
              class="modal__input"
              placeholder="Введите пароль"
              v-model="passwordR"
            />
          </div>
        </div>
      </div>
    </template>
    <template #footer>
      <div class="reg__btn">
        <button class="reg__button" @click="reg">Зарегистрироваться</button>
      </div>
      <div class="not__acc">
        <p class="haveacc__main">Есть аккаунт?</p>
        <a class="haveacc__href" @click="openLog()">Войти</a>
      </div>
      <div class="haveacc__btn">
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
          <button class="haveacc__button">
            <img
              src="./assets/img/steamico.svg"
              alt=""
              style="width: 1.25vw; margin-right: 0.52vw"
            />Войти через Steam
          </button>
        </form>
      </div>
    </template>
  </reg-modal>

  <money-modal> </money-modal>

  <output-modal> </output-modal>

  <payment-error>
    <template #header>
      <div class="modal__header">
        <img src="@/assets/img/opswallet.png" alt="" style="width: 6.25vw" />
      </div>
    </template>
    <template #body>
      <div class="modal__body">
        <p class="modal__text">Упс...</p>
        <p class="modal__text">Попробуйте другую платежную систему</p>
      </div>
    </template>
    <template #footer>
      <div class="modal__btn">
        <button class="modal__button" @click="closeError()">Понятно</button>
      </div>
    </template>
  </payment-error>
</template>
<script>
$(document).on("hidden.bs.modal", function (event) {
  if ($(".modal:visible").length) {
    $("body").addClass("modal-open");
  }
});
export default {
  methods: {
    openLog() {
      $("#Reg").modal("hide");
      $("#LogReg").modal("show");
    },
    openReg() {
      $("#LogReg").modal("hide");
      $("#Reg").modal("show");
    },
    closeError() {
      $("#PaymentError").modal("hide");
    },
    openTopUp() {
      $("#exampleModal").modal("hide");
      $("#Money").modal("show");
    },
    openSignIn() {
      $("#exampleModal").modal("hide");
      $("#LogReg").modal("show");
    },
  },
};
</script>
<style scoped>
.reg__btn {
  display: flex;
  justify-content: center;
}
.not__acc {
  display: flex;
  justify-content: center;
}
.haveacc__btn {
  display: flex;
  justify-content: space-around;
  margin-bottom: 2.71vw;
}
.haveacc__btn2 {
  margin-top: 1.98vw;
  display: flex;
  justify-content: center;
  margin-bottom: 2.71vw;
}
.reg__button {
  font-family: "Roboto";
  display: flex;
  font-weight: 400;
  font-size: 1.04vw;
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24;
  box-sizing: border-box;
  border-radius: 5px;
  align-items: center;
  color: #fff;
  padding: 0.94vw 8.18vw 0.94vw 8.18vw;
}
.haveacc__button {
  font-family: "Roboto";
  display: flex;
  font-weight: 400;
  font-size: 1.04vw;
  box-sizing: border-box;
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-sizing: border-box;
  border-radius: 5px;
  background: transparent;
  align-items: center;
  color: #fff;
  padding: 0.83vw 1.67vw 0.83vw 1.67vw;
}
.haveacc__href {
  cursor: pointer;
  font-weight: 400;
  font-size: 1.04vw;
  letter-spacing: 0.03em;
  text-decoration-line: underline;
  color: #f15a24;
  margin-left: 0.5vw;
}
.haveacc__main {
  font-weight: 400;
  font-size: 1.04vw;
  letter-spacing: 0.03em;
  color: #fff;
  text-align: center;
}
::placeholder {
  font-weight: 500;
  font-size: 1.25vw;
  color: rgba(247, 247, 247, 0.3);
}
.modal__btn {
  text-align: center;
}
.modal__inputs {
  padding-top: 4.17vw;
  display: flex;
  justify-content: center;
}
.modal__input {
  background: radial-gradient(
    82.39% 82.39% at 50% 50%,
    rgba(30, 29, 33, 0.4) 0%,
    rgba(60, 59, 63, 0.4) 100%
  );
  border: 1px solid #6d6d6d;
  box-sizing: border-box;
  border-radius: 5px;
  width: 26.61vw;
  height: 3.13vw !important;
  border: 0;
  outline: 0;
  color: #fff;
  padding-left: 1.15vw;
  font-size: 1.25vw;
  margin-bottom: 1.67vw;
}
.modal__label {
  font-weight: 500;
  font-size: 1.04vw;
  color: #fff;
}
.modal__signin {
  font-family: "Roboto";
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24;
  box-sizing: border-box;
  border-radius: 5px;
  padding: 0.94vw 11.77vw 0.94vw 11.77vw;
  font-weight: 400;
  font-size: 1.04vw;
  color: #fff;
  -webkit-clip-path: polygon(0 10%, 100% 0, 100% -90%, 0 100%);
  clip-path: polygon(10% 0, 0 100%, 90% 100%, 100% 0);
}
.logreg__main {
  font-family: "Impact";
  text-align: center;
  font-weight: 900;
  font-size: 1.25vw;
  letter-spacing: 0.025em;
  color: #fff;
  padding-top: 1.93vw;
}
.modal__href {
  color: #000;
}
.modal__href:hover {
  text-decoration: none;
}
.modal__button {
  background: #fff;
  border-radius: 5px;
  padding: 0.83vw 8.75vw 0.83vw 8.75vw;
  border: 0;
  font-weight: 400;
  font-size: 1.04vw;
  color: #000;
  text-align: center;
  margin-bottom: 1.2vw;
}
.modal__btn {
  padding-top: 0.45vw;
  text-align: center;
  padding-bottom: 0.45vw;
}
.modal__header {
  padding-left: 12.79vw;
  padding-right: 21.35vw;
  padding-top: 3.49vw;
}
.modal__body {
  padding-top: 3.02vw;
}
.modal__text {
  font-family: "Impact";
  font-weight: 400;
  font-size: 1.04vw;
  text-align: center;
  color: #fff;
}
.modal__textOps {
  margin-top: 1vw;
  font-family: "Impact";
  font-weight: 900;
  font-size: 1.25vw;
  text-align: center;
  color: #fff;
}
@media screen and (max-width: 1024px) {
  .modal__inputs {
    padding-top: 4.17vw;
    padding-left: 9.82vw;
    padding-right: 6.82vw;
  }
  .modal-body {
    font-size: 16px;
  }
}
@media screen and (max-width: 768px) {
  .modal__inputs {
    padding-top: 4.17vw;
    padding-left: 17.82vw;
    padding-right: 19.82vw;
  }
}
@media screen and (max-width: 480px) {
  .reg__btn {
    padding-left: 28.6vw;
    padding-right: 2.6vw;
  }
  .reg__button {
    font-size: 2vw;
    width: 0;
    padding: 0.83vw 27.23vw 0.83vw 8.23vw;
  }
  .modal__textOps {
    font-family: "Roboto";
    font-size: 3vw;
  }
  .modal__text {
    font-size: 3.5vw !important;
  }
  .modal__button {
    font-size: 2.4vw !important;
  }
  .modal__header {
    padding-left: 38.79vw !important;
  }
  .modal__header img {
    width: 16.25vw !important;
  }
  .logreg__main {
    font-size: 3.5vw !important;
  }
  .modal__label {
    font-size: 3.2vw !important;
  }
  .modal__input {
    height: 3.9vw !important;
    font-size: 2.5vw !important;
    width: 62.62vw !important;
  }
  .modal__inputs {
    padding-left: 12.82vw;
    padding-right: 2.8200000000000003vw;
  }
  .modal__signin,
  .haveacc__button,
  .haveacc__href,
  .haveacc__main {
    font-size: 2.5vw !important;
  }
  .haveacc__button img {
    width: 5.39vw !important;
  }
}
</style>
