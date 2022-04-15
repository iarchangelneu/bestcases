<template>
  <a name="FAQ"></a>
  <div class="faq__text">
        <img src="@/assets/img/faq.png" style="width:30.26vw" alt="">
      </div>
  <div class="faq">
    <div class="faq__bg pl__pr">
      <div class="faq__flex row">
        <div class="accordion col" id="accordionExample">
          <div class="card">
            <div class="card-header" id="headingOne">
              <div class="coll__flex">
                <h2 class="mb-0">
                  <button
                    class="btn btn-link btn-block text-left"
                    type="button"
                    data-toggle="collapse"
                    data-target="#collapse0"
                    aria-expanded="true"
                    aria-controls="collapse0"
                    id="faqBtn0"
                  >
                    Что я могу сделать с выигранными скинами?
                  </button>
                </h2>
                <div class="p" id="faqPlus0">+</div>
              </div>
            </div>

            <div
              id="collapse0"
              class="collapse"
              aria-labelledby="headingOne"
              data-parent="#accordionExample"
            >
              <div class="card-body">
               Вы можете продать их на нашем сайте или вывести скины к себе в инвентарь steam
              </div>
            </div>
          </div>
          <div class="card">
            <div class="card-header" id="headingTwo">
              <div class="coll__flex">
                <h2 class="mb-0">
                  <button
                    class="btn btn-link btn-block text-left"
                    type="button"
                    data-toggle="collapse"
                    data-target="#collapse1"
                    aria-expanded="true"
                    aria-controls="collapse1"
                    id="faqBtn1"
                  >
                    Когда мне придёт обмен?
                  </button>
                </h2>
                <div class="p" id="faqPlus1">+</div>
              </div>
            </div>
            <div
              id="collapse1"
              class="collapse"
              aria-labelledby="headingTwo"
              data-parent="#accordionExample"
            >
              <div class="card-body">
                Предметы отправляются практически моментально, независимо от типа предмета<br>
                 - армейское это качество или тайное, любой предмет будет доставлен за считанные секунды!
              </div>
            </div>
          </div>
          <div class="card">
            <div class="card-header" id="headingThree">
              <div class="coll__flex">
                <h2 class="mb-0">
                  <button
                    class="btn btn-link btn-block text-left"
                    type="button"
                    data-toggle="collapse"
                    data-target="#collapse2"
                    aria-expanded="true"
                    aria-controls="collapse2"
                    id="faqBtn2"
                  >
                     Что будет, если я отклоню обмен от бота?
                  </button>
                </h2>
                <div class="p" id="faqPlus2">+</div>
              </div>
            </div>
            <div
              id="collapse2"
              class="collapse"
              aria-labelledby="headingThree"
              data-parent="#accordionExample"
            >
              <div class="card-body">
                Если Вы отклоните обмен, сделаете встречное предложение боту,<br>
                 либо не примите в течение часа, то Ваш предмет не будет выслан,<br>
                  не будет продан, а средства не будут возвращены
              </div>
            </div>
          </div>
          <div class="card">
            <div class="card-header" id="headingFour">
              <div class="coll__flex">
                <h2 class="mb-0">
                  <button
                    class="btn btn-link btn-block text-left"
                    type="button"
                    data-toggle="collapse"
                    data-target="#collapse3"
                    aria-expanded="true"
                    aria-controls="collapse3"
                    id="faqBtn3"
                  >
                     У меня есть деньги в Steam, но сайт их не видит. Почему?
                  </button>
                </h2>
                <div class="p" id="faqPlus3">+</div>
              </div>
            </div>
            <div
              id="collapse3"
              class="collapse"
              aria-labelledby="headingFour"
              data-parent="#accordionExample"
            >
              <div class="card-body">
                Деньги на сайт нужно пополнять отдельно. Чтобы пополнить баланс нужно пройти авторизацию,<br>
                 перейти на страницу пополнения баланса, ввести нужную сумму и нажать кнопку "Пополнить"
              </div>
            </div>
          </div>
          <div class="card">
            <div class="card-header" id="headingFive">
              <div class="coll__flex">
                <h2 class="mb-0">
                  <button
                    class="btn btn-link btn-block text-left"
                    type="button"
                    data-toggle="collapse"
                    data-target="#collapse4"
                    aria-expanded="true"
                    aria-controls="collapse4"
                    id="faqBtn4"
                  >
                     Как формируется цена предметов?
                  </button>
                </h2>
                <div class="p" id="faqPlus4">+</div>
              </div>
            </div>
            <div
              id="collapse4"
              class="collapse"
              aria-labelledby="headingFour"
              data-parent="#accordionExample"
            >
              <div class="card-body">
                Цена на скины формируется автоматически. В расчёт берутся данные разных торговых площадок
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    collaps(a) {
      var faqBtn = document.querySelectorAll(`#faqBtn${a}`);
      var faqPlus = document.querySelectorAll(`#faqPlus${a}`);
      if (!faqBtn[0].classList.contains("collapsed")) {
        for (let i = 0; i < faqBtn.length; i++) {
          faqPlus[i].innerHTML = "-";
        }
      } else {
        faqPlus[0].innerHTML = "+";
      }
    },
  },
  mounted() {
    for (let i = 0; i < 5; i++) {
      $(`#collapse${i}`).on("show.bs.collapse", function () {
        document.querySelector(`#faqPlus${i}`).innerHTML = "-";
      });
      $(`#collapse${i}`).on("hide.bs.collapse", function () {
        document.querySelector(`#faqPlus${i}`).innerHTML = "+";
      });
      document.querySelector(`#faqPlus${i}`).onclick = () => {
        $(`#collapse${i}`).collapse("toggle");
      };
    }
  },
};
</script>

<style scoped>
.card-body {
  font-family: "Roboto";
  background: #1A1814 !important;
  color: #fff;
  font-weight: 400;
  font-size: 1.25vw;
}
.coll__flex {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.btn-link {
  outline: none;
  font-family: "Roboto";
  color: #fff;
  font-weight: 400;
  font-size: 1.25vw;
}
.p {
  width: 5.21vw;
  font-size: 2.34vw;
  color: #fff;
  background: #eac48b;
  padding: 0 1.77vw 0 1.77vw;
  cursor: pointer;
}
.card-header {
  background: #141416;
  box-sizing: border-box;
  border-radius: 6px;
  padding: 0;
}
.card {
  box-sizing: border-box;
  border-radius: 5px;
  border: 1px solid #eac48b !important;
  margin-bottom: 1.25vw;
}
.faq__flex {
  display: flex;
}
.faq__text {
  margin-top: 13.13vw;
  margin-bottom: 2.92vw;
  display: flex;
  justify-content: center;
}
.faq__answer {
  font-weight: 400;
  font-size: 1.25vw;
  color: #fff;
}
.faq {
  margin-top: 5vw;
  margin-bottom: 10.78vw;
}
.faq__main {
  margin-left: 1.25vw;
  font-weight: 900;
  font-size: 2.08vw;
  letter-spacing: 0.025em;
  color: #ffffff;
  text-align: left;
}
.pl__pr {
  padding-left: 5.21vw;
  padding-right: 5.21vw;
}
summary::-webkit-details-marker {
  display: none;
}
summary::-moz-list-bullet {
  list-style-type: none;
}
summary::marker {
  display: none;
}
summary {
  display: inline-block;
  padding: 0.3em 0.5em 0.3em 1.09vw;
  font-weight: 400;
  font-size: 1.25vw;
  cursor: pointer;
  color: #fff;
}
summary:before {
  content: "+";
  margin-right: 0.3em;
}
details[open] > summary:before {
  content: "–";
}
details[open] > summary {
  color: #fff;
}
summary ~ * {
  padding: 0 1em 0 1em;
}
summary:focus {
  outline: 0;
  box-shadow: inset 0 0 1px rgba(0, 0, 0, 0.3), inset 0 0 2px rgba(0, 0, 0, 0.3);
}
details {
  background: rgba(44, 109, 245, 0.2);
  border: 1px solid #2c6df5;
  box-sizing: border-box;
  border-radius: 5px;
  display: block;
  margin-bottom: 1.56vw;
  outline: 0;
}
@media screen and (max-width: 480px) {
  .p {
    height: 13vw;
    border-radius: 0;
    padding: 4.77vw 1.77vw 1.77vw 1.77vw;
  }
  .btn-link,
  .card-body {
    font-size: 2vw;
  }
  .faq__text img {
    width: 62vw !important;
  }
  .faq__main {
    font-size: 2.55vw;
  }
  summary,
  .faq__answer {
    font-size: 2.5vw;
  }
}
</style>