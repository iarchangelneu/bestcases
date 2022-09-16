<template>
  <div class="main" v-if="IsLogged">
    <div class="logo__cab">
      <img src="@/assets/img/cab.svg" style="width: 20.83vw" alt="" />
    </div>
    <div class="user">
      <div class="user__info">
        <div class="user__info-group">
          <img
            src="@/assets/img/fullsavatar.png"
            alt=""
            style="width: 8.33vw"
            class="user__ava"
          />
          <div class="user__margin" style="margin-left: 2.08vw">
            <p class="user__info-name">{{ USER_NAME }}</p>
            <a href="#" class="steam__href">
              <img
                src="@/assets/img/steamico.svg"
                style="width: 1.46vw"
                class="steam__ico"
              />
              {{ USER_NAME }}
            </a>
          </div>
        </div>
      </div>
      <div class="user__credits">
        <div class="user__credits-money">
          <img src="@/assets/img/walletlc.svg" style="width: 2.08vw" alt="" />
          <p class="user__count" style="margin-left: 1vw">0 ₸</p>
        </div>
        <div class="user__credits-buttons">
          <button class="user__btn1" data-toggle="modal" data-target="#Money">
            Пополнить баланс
          </button>
          <button
            class="user__btn"
            data-toggle="modal"
            data-target="#OutputMoney"
          >
            Вывести средства
          </button>
        </div>
      </div>
    </div>

    <div class="user__settings">
      <hr />
      <div class="user__links row">
        <div class="col">
          <div class="user__password pt-pb">
            <div class="user__password-input">
              <label for="current__password" class="title"
                >Текущий пароль</label
              >
              <input
                type="password"
                name="current__password"
                id="current__password"
                class="user-input"
              />
            </div>

            <div class="user__password-input">
              <label for="new__password" class="title">Новый пароль</label>
              <input
                type="password"
                name="new__password"
                id="new__password"
                class="user-input"
              />
            </div>

            <div>
              <label for="accept__password" class="title"
                >Подвердите пароль</label
              >
              <input
                type="password"
                name="accept__password"
                id="accept__password"
                class="user-input"
              />
            </div>
            <button class="user__btn">Сменить пароль</button>
          </div>
        </div>
        <div class="user__links-trade pt-pb col">
          <div>
            <p class="title">Трейд-ссылка</p>
            <a href="#" class="howget">Как получить?</a>
          </div>
          <div>
            <input
              type="text"
              placeholder="https://steamcommunity.com/tradeoffer/new/?partner=969138412&token=NJff8Nnr"
              name="trade"
              class="user-input"
            />
            <img
              src="@/assets/img/chain.svg"
              style="width: 1.67vw"
              class="chain"
            />
          </div>
          <div class="user__links-email pt-pb">
            <div class="user__password-input" style="flex-direction: row">
              <p class="title">E-mail</p>
              <img src="@/assets/img/pen.svg" style="width: 1.04vw" alt="#" />
            </div>
            <input
              type="email"
              placeholder="alex_krrr777@csmarket.com"
              class="user-input"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
  <p class="auth" v-else>Авторизуйтесь</p>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
export default {
  computed: {
    ...mapGetters(["IsLogged", "USER_NAME"]),
  },
};
</script>

<style scoped>
.logo__cab {
  display: flex;
  justify-content: center;
}
.auth {
  text-align: center;
  font-size: 6vw;
  color: #fff;
  padding-top: 9vw;
}
.howget {
  font-weight: 400;
  font-size: 0.83vw;
  text-decoration: underline;
  color: #fff;
  margin-right: 1.4vw;
}
.chain {
  position: absolute;
  left: -2.2vw;
}
::placeholder {
  font-size: 1.04vw;
}
.main {
  padding-top: 9.38vw;
  padding-left: 5.21vw;
  padding-right: 5.21vw;
}
.lc {
  font-weight: 900;
  font-size: 2.08vw;
  text-align: center;
  color: #fff;
}
.user {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 2rem;
}
.user__info {
  display: flex;
  align-items: center;
}
.user__info img {
  max-width: 8.33vw;
  border-radius: 100%;
}
.user__info-group {
  display: flex;
  padding-left: 2rem;
  padding-bottom: 2rem;
  align-items: center;
}
.user__info-group a {
  padding: 0.5rem;
  text-decoration: none;
  font-weight: 400;
  font-size: 1.25vw;
  color: #fff;
  opacity: 0.5;
  line-height: 1.46vw;
}
.user__info-name {
  padding: 1rem 0.7rem;
  font-weight: 600;
  font-size: 1.67vw;
  line-height: 1.67vw;
  color: #fff;
}
.user__credits {
  height: 8.33vw;
  align-items: center;
  flex-wrap: wrap;
}
.user__credits-money {
  display: flex;
  min-width: 8.33vw;
  align-items: baseline;
  justify-content: flex-end;
  margin: 0 2rem;
}
.user__credits-money p {
  font-weight: 500;
  font-size: 2.08vw;
  line-height: 1.25vw;
  color: #fff;
}
.user__credits-buttons {
  display: flex;
}
.user__btn1 {
  font-family: "Roboto";
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24;
  box-sizing: border-box;
  border-radius: 5px;
  -webkit-clip-path: polygon(0 10%, 100% 0, 100% -90%, 0 100%);
  clip-path: polygon(10% 0, 0 100%, 90% 100%, 100% 0);
  color: #fff;
  font-size: 1.04vw;
  font-weight: 400;
  margin-right: 2vw;
  padding: 0.94vw 2.71vw 0.94vw 2.71vw;
}
.user__btn {
  font-family: "Roboto";
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24;
  box-sizing: border-box;
  border-radius: 5px;
  -webkit-clip-path: polygon(0 10%, 100% 0, 100% -90%, 0 100%);
  clip-path: polygon(10% 0, 0 100%, 90% 100%, 100% 0);
  color: #fff;
  font-size: 1.04vw;
  font-weight: 400;
  margin-right: 2vw;
  padding: 0.94vw 2.71vw 0.94vw 2.71vw;
}
.user__credits-buttons button {
  min-width: 14.58vw;
  box-sizing: border-box;
}
hr {
  background: rgba(255, 255, 255, 0.1);
  opacity: 0.1;
}
.user__settings {
  margin: 0 2rem;
}
.user__links {
  display: flex;
  flex-wrap: wrap;
  gap: 3em;
}
.user__links-trade {
  padding: 1rem 0;
  width: 50%;
  gap: 1rem;
}
.user__links-trade > div {
  display: flex;
  justify-content: space-between;
}

.user-input {
  height: 3.13vw;
  width: 100%;
  border: 0;
  padding: 5px;
  color: rgba(255, 255, 255, 0.3);
  background: radial-gradient(
    82.39% 82.39% at 50% 50%,
    rgba(30, 29, 33, 0.4) 0%,
    rgba(60, 59, 63, 0.4) 100%
  );
  border: 1px solid #6d6d6d;
  box-sizing: border-box;
  border-radius: 5px;
}
.title {
  font-weight: 500;
  font-size: 1.04vw;
  line-height: 1.25vw;
  color: #fff;
}
.pt-pb {
  padding: 2rem 0;
}
.user__links-trade img {
  position: relative;
  right: 0;
}
.user__links-email {
  display: flex;
  flex-direction: column;
  width: 18.23vw;
  gap: 1rem;
}
.user__links-email div {
  display: flex;
  justify-content: space-between;
}
.user__password {
  display: flex;
  width: 26.04vw;
  flex-direction: column;
  gap: 1em;
}
.user__password-input {
  display: flex;
  flex-direction: column;
  gap: 1em;
}
.pd-1 {
  padding: 0.5em 0;
}
@media screen and (max-width: 768px) {
  .user {
    margin: 0;
  }
  hr {
    margin: 0;
  }
  .user__password-input p {
    margin: 0;
  }
}
@media screen and (max-width: 480px) {
  .user__count {
    font-size: 4vw !important;
    margin-bottom: 7vw;
  }
  .user__margin {
    margin-left: 7vw !important;
  }
  .steam__ico {
    width: 4vw !important;
  }
  .user__btn img {
    width: 3.5vw !important;
  }
  .user__btn,
  .user__btn1 {
    font-size: 2vw;
    margin-bottom: 1vw;
  }
  .user__info-name,
  .steam__href,
  .title,
  .howget {
    font-size: 2vw !important;
  }
  .howget {
    margin-top: -1vw;
  }
  .user__password-input img {
    width: 3vw !important;
    margin-top: -5vw;
  }
  .user-input {
    height: 6vw;
  }
  .user__info-name {
    margin-left: -2vw;
  }
  .user__info img {
    max-width: 13vw;
  }
  .user__info-group {
    padding-bottom: 0;
    padding-left: 1rem;
  }
  .user__ava {
    margin-left: 2vw;
    margin-top: 15vw;
    width: 20vw !important;
  }
}
</style>
