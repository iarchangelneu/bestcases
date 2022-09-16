<template>
  <div
    class="modal fade"
    id="OutputMoney"
    tabindex="-1"
    aria-labelledby="OutputMoney"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-centered">
      <div class="modal-contents2">
        <div class="modal-header">
          <div class="money__main">
            <p>Вывод средств</p>
            <div class="money__type">
              <div class="money__typecontent">
                <button class="money__btn" @click="topUp()">
                  Пополнение баланса
                </button>
                <button class="money__btn money__active">Вывод средств</button>
              </div>
            </div>
          </div>
        </div>
        <div class="modal-body">
          <div class="money__system">
            <div class="warning">
              <img
                src="../assets/img/warning.svg"
                alt=""
                style="width: 1.4vw; margin-right: 0.26vw"
              />
              <p class="warning__text">
                В случае указание неправильного номера кошелька средства не
                возвращаются.
              </p>
            </div>
            <div class="warning">
              <img
                src="../assets/img/warning.svg"
                alt=""
                style="width: 1.4vw; margin-right: 0.26vw"
              />
              <p class="warning__text">
                Процесс обработки заявки обычно занимает меньше часа, но может
                занять до 3-х рабочих дней.
              </p>
            </div>
            <p class="system__main">Порядок действий для пополнения баланса</p>
            <p class="money__text">1. Выберите платежную систему</p>
            <div class="system__type">
              <div
                :class="[
                  'type__img__one',
                  { payment__active: payment == 'onevision' },
                ]"
                @click="payment = 'onevision'"
              >
                <img
                  src="../assets/img/one__vision.png"
                  alt=""
                  class="pay_img"
                />
              </div>
              <div
                data-toggle="modal"
                data-target="#PaymentError"
                :class="[
                  'type__img__one',
                  { payment__active: payment == 'visa' },
                ]"
                @click="payment = 'visa'"
              >
                <img src="../assets/img/visa.png" alt="" class="pay_img" />
              </div>
              <div
                data-toggle="modal"
                data-target="#PaymentError"
                :class="[
                  'type__img__one',
                  { payment__active: payment == 'mastercard' },
                ]"
                @click="payment = 'mastercard'"
              >
                <img
                  src="../assets/img/mastercard.png"
                  alt=""
                  style=""
                  class="pay_img"
                />
              </div>
            </div>
            <div class="money__text__block">
              <p class="money__text">
                2. Подтвердите Ваше согласие с правилами нашей системы
              </p>
              <div class="money__checkbox">
                <input type="checkbox" id="policy" name="policy" />
                <label for="policy" class="money__label"
                  >Я согласен с
                  <a href="/terms">пользовательским соглашением</a> и
                  <a href="/privacy">политикой конфиденциальности</a></label
                >
                <p class="money__text mt">
                  3. Введите сумму, которую Вы хотите вывести на свой счет
                </p>
              </div>
            </div>
          </div>
        </div>
        <div class="modal-footer">
          <div class="money__complete">
            <input
              v-model="paySum"
              type="text"
              name="money"
              id="money"
              class="money__input"
              placeholder="Cумма ₸"
            />
            <button class="complete__btn" @click="purchase">Вывести</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      payment: "",
      paySum: '',
    };
  },
  methods: {
    topUp() {
      $("#OutputMoney").modal("hide");
      $("#Money").modal("show");
    },
    purchase(){
        if(this.paySum != ''){
          axios
          .post('https://realcases.kz/api/vision_pay/', {cost: this.paySum})
          .then((res) => {
              console.log(res)
              window.location.href=res.data.url
          })
          .catch((error) => {
            console.error(error);
          });
        }
        else{
          alert('Введите сумму пополнения!')
        }
      },
  },
};
</script>

<style scpoed>
.modal-contents2 {
  background: #1a1814;
  border: 1px solid rgba(234, 196, 139, 0.5);
  box-sizing: border-box;
  border-radius: 5px;
  position: relative;
  display: flex;
  flex-direction: column;
  width: 100%;
  pointer-events: auto;
  outline: 0;
}
.modal-body {
  margin-top: -2.5vw;
}
.warning {
  display: flex;
  align-items: flex-start;
}
.warning__text {
  font-family: "Roboto";
  font-weight: 400;
  font-size: 0.83vw;
  color: #fff;
}
.money__complete {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.mt {
  margin-top: 2.5vw;
}
.money__checkbox {
  margin-top: 2.5vw;
}
input[type="checkbox"] {
  transform: scale(1.5);
  padding: 0.52vw;
}
.money__label a {
  text-decoration: underline;
  color: #fff;
}
.type__img__visa {
  border: 3px solid #f7f7f7;
  box-sizing: border-box;
  border-radius: 7px;
  margin-right: 4.69vw;
  padding: 2.45vw 1.77vw 2.45vw 1.77vw;
  cursor: pointer;
}
.type__img__master {
  border: 3px solid #f7f7f7;
  box-sizing: border-box;
  border-radius: 7px;
  padding: 1.04vw 1.77vw 1.04vw 1.77vw;
  cursor: pointer;
}

.system__type {
  display: flex;
  margin-top: 2.08vw;
}
.money__active {
  background: #eac48b !important;
  border-radius: 5px;
  text-align: center;
}
.money__btn {
  z-index: 4;
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
  padding: 0.63vw 1.02vw 0.63vw 1.02vw;
}
.modal-dialog {
  min-width: 41.67vw;
}
.modal-header,
.modal-footer {
  border-bottom: 0;
  border-top: 0;
}
.modal-footer {
  display: contents;
}
@media screen and (max-width: 480px) {
  .warning__text {
    font-size: 2.5vw !important;
  }
  .warning img {
    width: 4.08vw !important;
  }
}
</style>