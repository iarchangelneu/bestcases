<template>
  <div class="main" v-if="IsLogged">
    <p class="lc">Личный кабинет</p>
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
          <img src="img/wallet.svg" alt="" />
          <p class="user__count">0 ₸</p>
        </div>
        <div class="user__credits-buttons">
          <button class="user__btn" data-toggle="modal" data-target="#Money">
            <img
              src="@/assets/img/dollar.svg"
              alt=""
              style="width: 1.25vw"
            />Пополнить баланс
          </button>
          <button
            class="user__btn"
            style="background: rgba(44, 109, 245, 0.2)"
            data-toggle="modal"
            data-target="#OutputMoney"
          >
            <img
              src="@/assets/img/money.svg"
              alt=""
              style="width: 1.2vw"
            />Вывести средства
          </button>
        </div>
      </div>
    </div>

    <div class="user__settings">
      <hr />
      <div class="user__links">
        <div class="user__links-trade pt-pb">
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
      <hr />
      <div class="user__password pt-pb">
        <div class="user__password-input">
          <label for="current__password" class="title">Текущий пароль</label>
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
          <label for="accept__password" class="title">Подвердите пароль</label>
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
  display: flex;
  height: 8.33vw;
  align-items: center;
  flex-wrap: wrap;
}
.user__credits-money {
  display: flex;
  min-width: 8.33vw;
  align-items: center;
  justify-content: space-evenly;
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
  flex-direction: column;
  justify-content: space-evenly;
  /* align-content: center; */
  height: 7.29vw;
}
.user__btn {
  text-align: center;
  color: #fff;
  border-radius: 5px;
  background-color: #2c6df5;
  border: 1px solid #2c6df5;
  display: flex;
  align-content: center;
  justify-content: center;
  column-gap: 1.04vw;
  align-items: center;
  font-size: 1.04vw;
  line-height: 1.2vw;
  padding: 0.83vw 2.08vw 0.83vw 2.08vw;
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
  display: flex;
  width: 50%;
  gap: 1rem;
  flex-direction: column;
}
.user__links-trade > div {
  display: flex;
  justify-content: space-between;
}

.user-input {
  height: 4.08vw;
  width: 100%;
  border: 0;
  padding: 5px;
  color: rgba(255, 255, 255, 0.3);
  background: #141721;
  border: 1px solid #246bff;
  box-sizing: border-box;
  box-shadow: 0px 0px 10px #2c6df5;
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
@media screen and (max-width: 480px) {
  .user__count{
    font-size: 4vw !important;
    margin-bottom:7vw;
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
  .user__btn {
    font-size: 2vw;
    margin-bottom: 1vw;
  }
  .user__info-name,
  .steam__href, .title, .howget {
    font-size: 2vw !important;
  }
  .howget{
    margin-top: -1vw;
  }
  .user__password-input img{
    width:3vw !important;
    margin-top: -5vw;
  }
  .user-input{
    height: 6vw;
  }
  .user__info-name {
    margin-left: -2vw;
  }
  .user__info img {
    max-width: 13vw;
  }
  .user__info-group{
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
