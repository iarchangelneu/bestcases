<template>
  <div class="stock" style="overflow-x: hidden; overflow-y: hidden">
    <div class="inner">
      <div class="stock__images row">
        <div class="stock__left col">
          <p class="stock__main">
            Участвуй в акциях<br />
            на нашем сайте
          </p>
          <p class="stock__sec">
            BEST CASES это лучшие кейсы с большими<br />
            скидками по всему СНГ
          </p>
          <div class="stock__buttons">
            <button class="stock__btnright">Перейти к кейсам</button>
          </div>
        </div>
        <img
          src="@/assets/img/scroll.svg"
          style="width: 1.41vw; margin-top: 28vw"
          alt=""
        />
        <div class="stock__right col">
          <!-- <img
            src="@/assets/img/bgstock.png"
            alt=""
            style="width: 47.66vw"
            class="stock__bg"
          /> -->
        </div>
      </div>
    </div>
  </div>
  <div class="whywe">
    <div class="whywe__title">
      <img src="@/assets/img/whywe.svg" style="width: 18.75vw" alt="" />
    </div>
    <div class="whywe__content">
      <div class="whywe__items">
        <img src="@/assets/img/target.png" style="width: 13.23vw" alt="" />
        <p class="whywe__items__title">Частые выигрыши</p>
        <p class="whywe__items__desc">
          BestCases предлагает вам<br />
          частые и ежедневные<br />
          выигрыши
        </p>
      </div>
      <div class="whywe__items">
        <img src="@/assets/img/bank.png" style="width: 11.56vw" alt="" />
        <p class="whywe__items__title">Уникальные кейсы</p>
        <p class="whywe__items__desc">
          Цены на нашем сайте одни из<br />
          самых выгодных среди<br />
          аналогичных сайтов
        </p>
      </div>
      <div class="whywe__items">
        <img src="@/assets/img/sherif.png" style="width: 10.21vw" alt="" />
        <p class="whywe__items__title">Уникальные кейсы</p>
        <p class="whywe__items__desc">
          Огромное количество кейсов,<br />
          оружия и прочего снаряжения<br />
          по лучшей цене
        </p>
      </div>
    </div>
  </div>
  <div class="cases__sales">
    <img src="@/assets/img/sales.svg" style="width: 18.75vw" alt="" />
  </div>
  <div class="container-fluid">
    <div class="cases">
      <div class="cases__content">
        <div class="cases__cases">
          <div class="case__content">
            <img
              src="@/assets/img/magic.png"
              class="case1"
              alt=""
              style="width: 20.83vw"
            />
            <p class="case__desc">Магический кейс</p>
            <button class="case__btn">Купить за 9 900 ₸</button>
          </div>
          <div class="case__content">
            <img
              src="@/assets/img/toxic.png"
              class="case2"
              alt=""
              style="width: 21.98vw"
            />
            <p class="case__desc mtc">Кислотный кейс</p>
            <button class="case__btn">Купить за 11 900 ₸</button>
          </div>
          <div class="case__content">
            <img
              src="@/assets/img/ice.png"
              class="case3"
              alt=""
              style="width: 21.09vw"
            />
            <p class="case__desc">Ледяной кейс</p>
            <button class="case__btn">Купить за 5 490 ₸</button>
          </div>
          <div class="case__content">
            <img
              src="@/assets/img/gold.png"
              class="case4"
              alt=""
              style="width: 19.79vw"
            />
            <p class="case__desc mtc">Золотой кейс</p>
            <button class="case__btn">Купить за 11 200 ₸</button>
          </div>
        </div>
        <div class="cases__cases2">
          <div class="case__content2">
            <img
              src="@/assets/img/lucky.png"
              class="case1"
              alt=""
              style="width: 16.77vw"
            />
            <p class="case__desc">Магический кейс</p>
            <button class="case__btn">Купить за 9 900 ₸</button>
          </div>
          <div class="case__content2">
            <img
              src="@/assets/img/lifestyle.png"
              class="case2"
              alt=""
              style="width: 17.97vw"
            />
            <p class="case__desc mtc">Кислотный кейс</p>
            <button class="case__btn">Купить за 11 900 ₸</button>
          </div>
          <div class="case__content2">
            <img
              src="@/assets/img/danger.png"
              class="case3"
              alt=""
              style="width: 15.21vw"
            />
            <p class="case__desc">Ледяной кейс</p>
            <button class="case__btn" style="margin-top: 1.8vw">
              Купить за 5 490 ₸
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="popular__text__content">
    <img src="@/assets/img/popular__items.png" style="width: 24.38vw" alt="" />
  </div>
  <div class="popular__items">
    <div class="popular__weapons"></div>
    <div class="item__weapons__blocks">
      <div class="item__block">
        <div class="item__block__content">
          <img src="@/assets/img/brain.png" alt="" style="width: 13.02vw" />
          <p class="weapon__name" style="margin-top: 1.3vw">USP-S</p>
          <div class="weapon__price__content">
            <p class="weapon__from">от</p>
            <p class="weapon__price">9 000 ₸</p>
          </div>
        </div>
      </div>
      <div class="item__block">
        <div class="item__block__content">
          <img src="@/assets/img/m4a4.png" alt="" style="width: 13.02vw" />
          <p class="weapon__name" style="margin-top: 1.6vw">M4A4</p>
          <div class="weapon__price__content">
            <p class="weapon__from">от</p>
            <p class="weapon__price">13 590 ₸</p>
          </div>
        </div>
      </div>
      <div class="item__block">
        <div class="item__block__content">
          <img
            src="@/assets/img/web.png"
            alt=""
            style="width: 13.02vw; margin-top: -1.46vw"
          />
          <p class="weapon__name">Karambit Crimson Web</p>
          <div class="weapon__price__content">
            <p class="weapon__from">от</p>
            <p class="weapon__price">12 095 $</p>
          </div>
        </div>
      </div>
      <div class="item__block">
        <div class="item__block__content">
          <img src="@/assets/img/flame.png" alt="" style="width: 13.02vw" />
          <p class="weapon__name" style="margin-top: 1.6vw">Desert Eagle</p>
          <div class="weapon__price__content">
            <p class="weapon__from">от</p>
            <p class="weapon__price">81 590 ₸</p>
          </div>
        </div>
      </div>
      <div class="item__block">
        <div class="item__block__content">
          <img src="@/assets/img/butterfly.png" alt="" style="width: 13.02vw" />
          <p class="weapon__name">Butterfly Knife Doppler</p>
          <div class="weapon__price__content">
            <p class="weapon__from">от</p>
            <p class="weapon__price">13 109 $</p>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="stats__block">
    <div class="stats__img">
      <img src="@/assets/img/stats.png" style="width: 86.15vw" alt="" />
    </div>
    <div class="stats">
      <div class="stats__content">
        <p class="stats__title">Статистика</p>
        <div class="stats__block">
          <div style="margin-right: 4.17vw">
            <p class="stats__count">{{currentlyOpened}}</p>
            <p class="stats__name">Открытых кейсов</p>
          </div>
          <div>
            <p class="stats__count">{{usersAll}}</p>
            <p class="stats__name">Всего пользователей</p>
          </div>
        </div>
        <div class="stats__block">
          <div style="margin-right: 6.17vw">
            <p class="stats__count">{{usersOnline}}</p>
            <p class="stats__name">Онлайн сейчас</p>
          </div>
          <div>
            <p class="stats__count">{{contracts}}</p>
            <p class="stats__name">Контрактов</p>
          </div>
        </div>
      </div>
    </div>
  </div>
  <the-faq></the-faq>
</template>

<script>
export default {
  computed: {
    contracts(){
      let curDate = new Date();
      return (
        20000 +
        Math.floor(
          (Date.parse(curDate) - Date.parse("2022-04-03T13:51:50.417-07:00")) /
            60 /
            60 /
            24
        )
      );
    },
    currentlyOpened() {
      let curDate = new Date();
      return (
        500000 +
        Math.floor(
          (Date.parse(curDate) - Date.parse("2022-04-03T13:51:50.417-07:00")) /
            60 /
            60 /
            24
        )
      );
    },
    usersAll() {
      let curDate = new Date();
      return (
        120000 +
        Math.floor(
          (Date.parse(curDate) - Date.parse("2022-04-03T13:51:50.417-07:00")) /
            60 /
            60 /
            24
        )
      );
    },
    usersOnline() {
      let curDate = new Date();
      return Math.floor(7000 + Math.random() * (2000 - 1) + 1);
    },
  },
};
</script>

<style scoped>
.stats__img {
  margin-top: 9.9vw;
  margin-left: 6.08vw;
}
.stats__block {
  position: relative;
}
.stats__name {
  font-family: "Roboto";
  font-weight: 400;
  color: #eac48b;
  font-size: 1.25vw;
}
.stats__count {
  font-family: "Allerta Stencil";
  font-weight: 400;
  font-size: 3.13vw;
  color: #fff;
}
.stats__title {
  font-size: 2.6vw;
  font-weight: 700;
  color: #eac48b;
  text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}
.stats__block {
  display: flex;
}
.stats {
  top: 13.02vw;
  right: 23.44vw;
  position: absolute;
  display: flex;
  justify-content: flex-end;
}
.case__content2 {
  margin-right: 5vw;
}
.whywe__items img {
  margin-left: 3.2vw;
}
.whywe__items__title {
  margin-top: 1.46vw;
  font-size: 1.67vw;
  font-weight: 700;
  text-align: center;
  color: #fff;
}
.whywe__items__desc {
  font-size: 1.04vw;
  font-weight: 500;
  text-align: center;
  color: #fff;
}
.whywe__content {
  padding-left: 13.02vw;
  padding-right: 13.02vw;
  display: flex;
  justify-content: space-between;
  margin-top: 5.21vw;
}
.whywe {
  margin-top: 7.81vw;
}
.whywe__title {
  display: flex;
  justify-content: center;
}
.mtc {
  margin-top: 1.5rem;
}
.weapon__price {
  font-weight: 400;
  font-size: 1.04vw;
}
.weapon__from {
  margin-right: 0.5vw;
  font-weight: 400;
  font-size: 1.04vw;
  color: rgba(255, 255, 255, 0.3);
}
.weapon__name {
  font-family: "Montserrat";
  font-weight: 900;
  font-size: 1.15vw;
}
.weapon__price__content {
  display: flex;
}
.item__block__content:hover {
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24;
}
.item__block__content {
  border: 1px solid #6d6d6d;
  box-sizing: border-box;
  border-radius: 5px;
  cursor: pointer;
  width: 17.45vw;
  height: 20.36vw;
  color: #fff;
  padding-top: 2.6vw;
  padding-left: 1.25vw;
  background: radial-gradient(
    82.39% 82.39% at 50% 50%,
    rgba(30, 29, 33, 0.4) 0%,
    rgba(60, 59, 63, 0.4) 100%
  );
}
.item__weapons__blocks {
  display: flex;
  justify-content: space-between;
}
.shit {
  margin-top: 2.6vw;
}
.popular__cases__item {
  text-align: center;
}
.cases__item__btn {
  background: #2c6df5;
  border-radius: 5px;
  color: #fff;
  border: 0;
  font-weight: 400;
  font-size: 1.25vw;
  padding: 0.63vw 2.6vw 0.63vw 2.6vw;
}
.cases__item__desc {
  font-weight: 400;
  font-size: 1.25vw;
  color: #fff;
}
.popular__cases__content {
  display: flex;
  align-items: center;
}
.popular__text {
  margin-left: 1.25vw;
  font-weight: 900;
  font-size: 2.08vw;
  color: #fff;
}
.popular__text__content {
  margin-top: 8.85vw;
  display: flex;
  justify-content: center;
}
.popular__items {
  padding-top: 7.81vw;
  padding-left: 5.21vw;
  padding-right: 5.21vw;
}
.case__btn {
  font-family: "Roboto";
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24;
  box-sizing: border-box;
  border-radius: 5px;
  color: #fff;
  padding: 0.94vw 3.02vw 0.94vw 3.02vw;
  font-weight: 400;
  font-size: 1.04vw;
  margin-top: 2.08vw;
  margin-bottom: 3.13vw;
  -webkit-clip-path: polygon(0 10%, 100% 0, 100% -90%, 0 100%);
  clip-path: polygon(10% 0, 0 100%, 90% 100%, 100% 0);
}
.case__desc {
  font-weight: 400;
  font-size: 1.25vw;
  color: #ffff;
}
.case__frame {
  margin-left: 13.44vw;
  font-weight: 400;
  font-size: 1.25vw;
  color: #fff;
  background: rgba(44, 109, 245, 0.2);
  border: 1px solid #2c6df5;
  box-sizing: border-box;
  border-radius: 5px;
  width: 5.21vw;
  padding: 0.52vw 1.25vw 0.52vw 1.25vw;
}
.cases__cases {
  padding-left: 1.04vw;
  text-align: center;
  display: flex;
}
.cases__cases2 {
  padding-left: 1.04vw;
  text-align: center;
  display: flex;
  justify-content: center;
}
.cases__href {
  color: #fff;
  font-weight: 400;
  font-size: 1.04vw;
}
.cases__sales__text {
  margin-left: 1.25vw;
  font-weight: 900;
  font-size: 2.08vw;
}
.cases__main {
  padding-left: 2.6vw;
  padding-right: 2.6vw;
  display: flex;
  justify-content: space-between;
  color: #fff;
}
.cases__sales {
  margin-top: 8.85vw;
  display: flex;
  justify-content: center;
}
.stock__buttons {
  padding-bottom: 6vw;
  margin-left: -26.79vw;
}
.stock__btnleft {
  background: #2c6df5;
  border-radius: 5px;
  border: 0;
  padding: 1.25vw 2.6vw 1.25vw 2.6vw;
  font-size: 1.04vw;
  color: #fff;
  margin-right: 1.25vw;
}
.stock__btnright {
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24;
  box-sizing: border-box;
  border-radius: 5px;
  padding: 1.09vw 4.58vw 1.09vw 4.58vw;
  font-size: 1.04vw;
  color: #fff;
  -webkit-clip-path: polygon(0 10%, 100% 0, 100% -90%, 0 100%);
  clip-path: polygon(10% 0, 0 100%, 90% 100%, 100% 0);
}
.stock__main {
  text-align: left;
  font-style: normal;
  font-weight: 900;
  font-size: 4.17vw;
}
.stock__sec {
  margin-bottom: 4.27vw;
  text-align: left;
  font-weight: 400;
  font-size: 1.25vw;
}
.linkwithout {
  outline: none;
  text-decoration: none;
}
.slct {
  position: absolute;
  left: 45%;
  bottom: 0;
}
.cases__popular__content {
  display: flex;
  justify-content: center;
}
.casesLeft {
  position: absolute;
  width: 1.35vw;
  left: 10px;
  top: 50%;
  cursor: pointer;
  z-index: 4;
}
.casesRight {
  position: absolute;
  width: 1.35vw;
  right: 10px;
  top: 50%;
  cursor: pointer;
  z-index: 4;
}
.cases_p {
  padding-bottom: 5.83vw;
}
.pl__pr {
  margin-left: 2.86vw;
  margin-right: 2.86vw;
}
.cases__price {
  font-weight: 800;
  font-size: 1.88vw;
  line-height: 2.5vw;
  text-align: center;
  letter-spacing: 0.065em;
  background: linear-gradient(83.8deg, #c62c44 15.62%, #ff0027 91.62%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-fill-color: transparent;
  text-shadow: 5px 4px 30px #9a1f36, 2px 4px 4px #9a1f36;
}
.cases__desc {
  font-size: 1.35vw;
  text-align: center;
  color: #fff;
}
.cases__popular {
  display: grid;
  margin-top: 3.96vw;
}
.cases__avatar {
  padding-top: 6.35vw;
}
.stock__btn {
  border: 0;
  background: linear-gradient(83.8deg, #c62c44 15.62%, #ff0027 91.62%);
  border-radius: 1.56vw;
  font-weight: 700;
  font-size: 1.46vw;
  color: #fff;
  padding: 0.89vw 1.46vw 0.89vw 1.46vw;
}
.stock__button {
  margin-left: 5vw;
  padding-bottom: 5.21vw;
}
.stock__button2 {
  padding-bottom: 5.21vw;
}
.stock__desc22 {
  font-weight: 700;
  font-size: 2.08vw;
  color: #fff;
}
.stock__desc2 {
  margin-left: 5vw;
  font-weight: 700;
  font-size: 2.08vw;
  color: #fff;
  margin-top: -10.15vw;
}
.stock__left {
  margin-top: 12.66vw;
  margin-left: 4.48vw;
}
.stock__left2 {
  margin-top: 4.53vw;
  margin-left: 4.48vw;
}
.stock__right2 {
  margin-top: 11.04vw;
}
.stock__images {
  display: flex;
  justify-content: space-between;
}
.stock {
  -webkit-background-size: cover;
  position: relative;
  height: 50.2vw !important;
}

.inner {
  padding-top: 6.46vw;
  background-image: url("@/assets/img/bgmarket.png");
  background-size: 100vw;
  position: relative;
  z-index: 3;
  color: #fff;
  text-align: center;
}
.cases {
  margin-top: 4.17vw;
  padding-left: 5.21vw;
  padding-right: 5.21vw;
  position: relative;
}

.cases__content {
  position: relative;
  /* padding-top: 12.19vw; */
}
.stock__text {
  text-shadow: 5px 4px 30px #561f8c, 2px 4px 4px #561f8c;
  color: #f7f7f7;
  font-weight: 800;
  font-size: 3.13vw;
}
hr {
  border: 3px solid #ffffff;
  box-shadow: 0px 2px 4px #9028f6;
  filter: blur(1px);
  width: 10.68vw;
  text-align: center;
}

@media screen and (max-width: 480px) {
  .item__block__content {
    height: 31.36vw;
  }
  .weapon__price,
  .weapon__from {
    font-size: 1.75vw;
  }
  .cases__item__desc,
  .cases__item__btn,
  .weapon__name {
    font-size: 2vw;
  }
  .popular__text {
    font-size: 2.55vw;
  }
  .popular__text__content img {
    width: 4vw !important;
  }
  .case__btn {
    font-size: 2vw;
  }
  .case4 {
    margin-bottom: -1vw;
  }
  .mtc {
    margin-top: 1.2vw;
  }
  .case__desc {
    font-size: 2vw;
  }
  .case1,
  .case2,
  .case3,
  .case4 {
    width: 19.67vw !important;
  }
  .case__frame {
    font-size: 2vw;
    margin-left: 10.44vw;
    width: 7.210000000000001vw;
  }
  .cases__content {
    background-size: 150.58vw;
  }
  .cases__href {
    margin-top: 2.2vw;
    font-size: 2vw;
  }
  .cases__sales__text {
    font-size: 2.8vw;
  }
  .cases__sales img {
    width: 4.67vw !important;
  }
  .stock__sec {
    font-family: "Roboto";
    font-size: 1.95vw;
  }
  .stock {
    height: 65.2vw !important;
    padding-top: 10vw;
  }
  .stock__desc,
  .stock__desc2 {
    font-size: 2.67vw;
  }
  .stock__left {
    margin-top: 4.66vw;
  }
  .inner {
    background-size: 100vw;
  }
  .stock__text {
    font-size: 3.93vw;
  }
  .stock__button {
    margin-top: -4vw;
    padding-bottom: 0;
  }
  .stock__buttons {
    margin-left: -0.78vw;
  }
  .stock__btnleft,
  .stock__btnright {
    font-size: 1.7vw;
  }
  .cases__mainimg {
    margin-left: 29vw !important;
  }
  .cases__mainimg2 {
    margin-left: 26vw !important;
  }
  .stock__btn {
    font-size: 2.67vw;
  }
  .stock__img {
    width: 4.08vw !important;
  }
  hr {
    border: 2px solid #ffffff;
  }
  .cases__popular {
    flex-wrap: wrap;
  }
  .cases__popular__content img {
    width: 27vw !important;
  }
  .cases__avatar img {
    width: 7vw !important;
  }
  .cases__desc {
    font-size: 3.2vw;
  }
  .cases__price {
    font-size: 3.5vw;
  }
}
@media screen and (max-width: 320px) {
  .inner {
    background-size: 101vw;
    padding-top: 11.6vw;
  }
  .stock__buttons {
    margin-left: -1.78vw;
  }
}
</style>
