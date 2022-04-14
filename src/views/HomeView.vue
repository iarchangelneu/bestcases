<template>
  <div class="stock" style="overflow-x: hidden; overflow-y: hidden">
    <div class="inner">
      <div class="stock__images row">
        <div class="stock__left col">
          <p class="stock__main">Обменивай лучшие скины</p>
          <p class="stock__sec">
            CS-MARKET.KZ - это грамотное управление<br />
            вашими кейсами в Steam. В нашем магазине<br />
            действуют постоянные скидки.
          </p>
          <div class="stock__buttons">
            <button class="stock__btnleft">Перейти в магазин</button>
            <button class="stock__btnright">Посмотреть кейсы</button>
          </div>
        </div>
        <div class="stock__right col">
          <img
            src="@/assets/img/bgstock.png"
            alt=""
            style="width: 47.66vw"
            class="stock__bg"
          />
        </div>
      </div>
    </div>
  </div>
  <div class="container-fluid">
    <div class="cases">
      <div class="cases__content">
        <div class="cases__main">
          <div class="cases__sales">
            <img src="@/assets/img/flash.svg" alt="" style="width:2.08vw"/>
            <p class="cases__sales__text">Акции и скидки</p>
          </div>
          <a href="/cases" class="cases__href">Посмотреть все кейсы</a>
        </div>
        <div class="cases__cases">
          <div class="case__content">
            <p class="case__frame">-10%</p>

            <img src="@/assets/img/magic.png" class="case1" alt="" style="width: 20.83vw" />
            <p class="case__desc">Магический кейс</p>
            <button class="case__btn">9 000 ₸</button>
          </div>
          <div class="case__content">
            <p class="case__frame">NEW</p>

            <img src="@/assets/img/toxic.png" class="case2" alt="" style="width: 21.98vw" />
            <p class="case__desc mtc">Кислотный кейс</p>
            <button class="case__btn">8 590 ₸</button>
          </div>
          <div class="case__content">
            <p class="case__frame">-5%</p>

            <img src="@/assets/img/ice.png" class="case3" alt="" style="width: 21.09vw" />
            <p class="case__desc">Ледяной кейс</p>
            <button class="case__btn">10 290 ₸</button>
          </div>
          <div class="case__content">
            <p class="case__frame">-10%</p>

            <img src="@/assets/img/gold.png" class="case4" alt="" style="width: 19.79vw" />
            <p class="case__desc mtc">Золотой кейс</p>
            <button class="case__btn">7 777 ₸</button>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="popular__items">
    <div class="popular__cases">
      <div class="popular__text__content">
        <img src="@/assets/img/star.svg" alt="" style="width: 2.08vw" />
        <p class="popular__text">Популярные кейсы</p>
      </div>
      <div class="popular__cases__content">
        <div class="popular__cases__item">
          <img src="@/assets/img/gamma.png" alt="" style="width: 16.93vw" />
          <p class="cases__item__desc">Кейс “Gamma”</p>
          <button class="cases__item__btn">4 500 ₸</button>
        </div>
        <div class="popular__cases__item">
          <img src="@/assets/img/rest.png" alt="" style="width: 16.93vw" />
          <p class="cases__item__desc">Кейс “Restricted”</p>
          <button class="cases__item__btn">6 500 ₸</button>
        </div>
        <div class="popular__cases__item">
          <img
            src="@/assets/img/inferno.png"
            alt=""
            style="width: 13.44vw; margin-left: 2.97vw; padding-top: 3.65vw"
          />
          <p class="cases__item__desc shit">Кейс “Inferno”</p>
          <button class="cases__item__btn">4 800 ₸</button>
        </div>
        <div class="popular__cases__item">
          <img
            src="@/assets/img/bravo.png"
            alt=""
            style="
              width: 13.44vw;
              margin-left: 4.58vw;
              margin-right: 2.86vw;
              padding-top: 3.65vw;
            "
          />
          <p class="cases__item__desc shit">Кейс “Bravo”</p>
          <button class="cases__item__btn">7 990 ₸</button>
        </div>
        <div class="popular__cases__item">
          <img src="@/assets/img/night.png" alt="" style="width: 16.93vw" />
          <p class="cases__item__desc">Кейс “Nightmare”</p>
          <button class="cases__item__btn">6 660 ₸</button>
        </div>
      </div>
    </div>
  </div>
  <div class="popular__items">
    <div class="popular__weapons">
      <div class="popular__text__content">
        <img src="@/assets/img/knife.svg" alt="" style="width: 2.08vw" />
        <p class="popular__text">Популярные предметы</p>
      </div>
    </div>
    <div class="item__weapons__blocks">
      <div class="item__block">
        <div class="item__block__content">
          <img src="@/assets/img/brain.png" alt="" style="width: 13.02vw" />
          <p class="weapon__name" style="margin-top:1.3vw">USP-S</p>
          <div class="weapon__price__content">
            <p class="weapon__from">от</p>
            <p class="weapon__price">9 000 ₸</p>
          </div>
        </div>
      </div>
      <div class="item__block">
        <div class="item__block__content">
          <img src="@/assets/img/m4a4.png" alt="" style="width: 13.02vw" />
          <p class="weapon__name" style="margin-top:1.6vw">M4A4</p>
          <div class="weapon__price__content">
            <p class="weapon__from">от</p>
            <p class="weapon__price">13 590 ₸</p>
          </div>
        </div>
      </div>
      <div class="item__block">
        <div class="item__block__content">
          <img src="@/assets/img/web.png" alt="" style="width: 13.02vw;margin-top:-1.46vw" />
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
          <p class="weapon__name" style="margin-top:1.6vw">Desert Eagle</p>
          <div class="weapon__price__content">
            <p class="weapon__from">от</p>
            <p class="weapon__price">81 590 ₸</p>
          </div>
        </div>
      </div>
      <div class="item__block">
        <div class="item__block__content">
          <img src="@/assets/img/butterfly.png" alt="" style="width: 13.02vw" />
          <p class="weapon__name">Butterfly Knife Doppler </p>
          <div class="weapon__price__content">
            <p class="weapon__from">от</p>
            <p class="weapon__price">13 109 $</p>
          </div>
        </div>
      </div>
    </div>
  </div>
  <the-faq></the-faq>
</template>

<script>
export default {
  methods: {},
  mounted() {},
};
</script>

<style scoped>
.mtc{
  margin-top: 1.5rem;
}
.weapon__price{
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
  font-weight: 900;
  font-size: 1.25vw;
}
.weapon__price__content {
  display: flex;
}
.item__block__content:hover{
background: radial-gradient(82.21% 62.79% at 50% 50%, #3F7AF5 0%, #03266F 100%) 
}
.item__block__content {
  cursor: pointer;
  width:17.45vw;
  height: 20.36vw;
  color: #fff;
  padding-top: 2.60vw;
  padding-left: 2.19vw;
  padding-right: 2.24vw;
  background: radial-gradient(
    82.39% 82.39% at 50% 50%,
    #1e1d21 0%,
    #3c3b3f 100%
  );
}
.item__weapons__blocks {
  display: flex;
  justify-content: space-between
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
  padding: 0.63vw 2.60vw 0.63vw 2.60vw;
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
  display: flex;
  align-items: baseline;
}
.popular__items {
  padding-top: 7.81vw;
  padding-left: 5.21vw;
  padding-right: 5.21vw;
}
.case__btn {
  background: #2c6df5;
  border-radius: 5px;
  color: #fff;
  padding: 0.63vw 2.60vw 0.63vw 2.60vw;
  border: 0;
  font-weight: 400;
  font-size: 1.25vw;
  margin-bottom: 3.13vw;
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
  display: flex;
  align-items: baseline;
}
.stock__buttons {
  margin-left: -14.79vw;
}
.stock__btnleft {
  background: #2c6df5;
  border-radius: 5px;
  border: 0;
  padding: 1.25vw 2.60vw 1.25vw 2.60vw;
  font-size: 1.04vw;
  color: #fff;
  margin-right: 1.25vw;
}
.stock__btnright {
  background: rgba(44, 109, 245, 0.2);
  border: 1px solid #2c6df5;
  border-radius: 5px;
  padding: 1.25vw 2.60vw 1.25vw 2.60vw;
  font-size: 1.04vw;
  color: #fff;
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
  margin-top: 5.63vw;
  padding-left: 5.21vw;
  padding-right: 5.21vw;
  position: relative;
}

.cases__content {
  position: relative;
  background: url("@/assets/img/act.png");
  background-size: 89.58vw;
  border-radius: 20px;
  padding-top: 2.6vw;
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
  .item__block__content{
    height: 31.36vw;
  }
  .weapon__price, .weapon__from{
    font-size: 1.75vw;
  }
  .cases__item__desc, .cases__item__btn, .weapon__name{
    font-size: 2vw;
  }
  .popular__text{
    font-size: 2.55vw;
  }
  .popular__text__content img{
    width: 4vw !important;
  }
  .case__btn{
    font-size: 2vw;
  }
  .case4{
    margin-bottom: -1vw;
  }
  .mtc{
    margin-top:1.2vw;
  }
  .case__desc{
    font-size: 2vw;
  }
  .case1, .case2, .case3, .case4{
    width: 19.67vw !important;
  }
  .case__frame{
    font-size: 2vw;
    margin-left: 10.44vw;
    width: 7.210000000000001vw;
  }
  .cases__content{
    background-size: 150.58vw;
  }
  .cases__href{
    margin-top: 2.2vw;
    font-size: 2vw;
  }
  .cases__sales__text{
    font-size: 2.8vw;
  }
  .cases__sales img{
    width:4.67vw !important;
  }
  .stock__sec{
    font-family: 'Roboto';
    font-size: 1.95vw;
  }
  .stock {
    height:65.2vw !important;
    padding-top:10vw;
  }
  .stock__desc,
  .stock__desc2 {
    font-size: 2.67vw;
  }
  .stock__left{
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
  .stock__buttons{
    margin-left: -0.78vw;
  }
  .stock__btnleft, .stock__btnright{
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
@media screen and (max-width: 320px){
  .inner{
    background-size: 101vw;
    padding-top: 11.6vw;
  }
  .stock__buttons{
    margin-left:-1.78vw
  }
}
</style>
