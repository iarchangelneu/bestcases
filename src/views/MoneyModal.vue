<template>
  <div
    class="modal fade"
    id="Money"
    tabindex="-1"
    aria-labelledby="Money"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-centered">
      <div class="modal-contents">
        <div class="modal-header">
          <div class="money__main">
            <p>Пополнение баланса</p>
            <div class="money__type">
              <div class="money__typecontent">
                <button class="money__btn money__active">
                  Пополнение баланса
                </button>
                <button class="money__btn" @click="outPut()">
                  Вывод средств
                </button>
              </div>
            </div>
          </div>
        </div>
        <div class="modal-body">
          <div class="money__system">
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
                  3. Введите сумму, на которую Вы хотите пополнить личный счет,
                  и нажмите на кнопку “Пополнить”. Вы будете переадресованы на
                  сайт платежной системы.
                </p>
              </div>
            </div>
          </div>
        </div>
        <div class="modal-footer">
          <div class="money__complete">
            <input
              type="number"
              name="money"
              id="money"
              v-model="paySum"
              class="money__input"
              placeholder="0 ₸"
            />
            <button class="complete__btn" @click="purchase">Пополнить баланс</button>
          </div>
          <div class="instr__link__cont mt-3 mb-3">
            <a class="instr__link" href="/instruction">Инструкция по использованию карты для платежа</a>
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
    outPut() {
      $("#Money").modal("hide");
      $("#OutputMoney").modal("show");
    },
    purchase(){
        if(this.paySum != ''){
          axios
          .post('https://bestcases.kz/api/vision_pay/', {cost: this.paySum})
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
.instr__link__cont{
  display: flex;
  align-items: flex-end;
  text-align: center;
  justify-content: center
}
.instr__link{
    font-weight: 500;
    font-size: 1.1vw;
    color: #fff;
    text-decoration: underline;
}
.instr__link:hover{
  color: #fff;
}
.money__typecontent {
  display: flex;
}
.complete__btn {
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24;
  box-sizing: border-box;
  border-radius: 5px;
  color: #fff;
  padding: 0.94vw 8.70vw 0.94vw 8.70vw;
  font-weight: 400;
  font-size: 1.04vw;
  border: 0;
  -webkit-clip-path: polygon(0 10%, 100% 0, 100% -90%, 0 100%);
  clip-path: polygon(10% 0, 0 100%, 90% 100%, 100% 0);
  margin-bottom:2.08vw;
}
::placeholder {
  color: #fff;
  font-size: 1.25vw;
  text-align: center;
}
.money__input {
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-sizing: border-box;
  border-radius: 5px;
  font-weight: 500;
  font-size: 2.08vw;
  color: #fff;
  width: 16.77vw;
  margin-bottom: 1.25vw;
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
.money__label {
  font-family: "Robotov";
  margin-left: 1.3vw;
  font-weight: 400;
  font-size: 0.73vw;
  color: #fff;
}
.money__label a {
  text-decoration: underline;
  color: #fff;
}
.money__text__block {
  margin-top: 0.65vw;
}
.type__img__one {
  border: 1px solid #f7f7f7;
  box-sizing: border-box;
  border-radius: 7px;
  margin-right: 1.69vw;
  padding: 0.52vw 5.56vw 0.52vw 1.56vw;
  cursor: pointer;
  width: 7.448vw;
  display: flex;
  align-items: center;
}
.payment__active {
  border: 1px solid #f15a24;
}
.pay_img {
  width: 3.8vw;
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
.money__text {
  font-family: "Roboto";
  font-weight: 400;
  font-size: 0.83vw;
  color: #fff;
}
.money__system {
  margin-top: 3.65vw;
  padding-left: 2.6vw;
}
.system__main {
  font-family: "Roboto";
  font-weight: 500;
  font-size: 1.04vw;
  color: #fff;
}
.money__type {
  margin-left: 8.5vw;
}
.money__main {
  font-weight: 900;
  font-size: 1.25vw;
  text-align: center;
  padding-top: 0.81vw;
  color: #fff;
}
.modal-dialog {
  min-width: 41.67vw;
}
.modal-contents {
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
.modal-header,
.modal-footer {
  border-bottom: 0;
  border-top: 0;
}
.modal-footer {
  display: contents;
}
@media screen and (max-width: 480px) {
  .pay_img {
    width: 10vw;
  }
  .money__type {
    margin-left: 22.5vw;
  }
  .money__main {
    font-size: 3.2vw !important;
  }
  .money__btn {
    font-size: 2.2vw !important;
    border: 1px solid #f7f7f7 !important;
  }
  .money__btn img {
    width: 2.8vw !important;
  }
  .system__main {
    font-size: 3vw !important;
  }
  .money__text {
    font-size: 2.3vw !important;
  }
  .money__label {
    font-size: 2.1vw !important;
  }
  input[type="checkbox"] {
    transform: scale(1) !important;
    margin-left: -13px;
  }
  .money__input {
    border: 1px solid rgba(247, 247, 247, 0.6) !important;
    font-size: 2.5vw !important;
    height: 7vw !important;
  }
  ::placeholder {
    font-size: 2.2vw !important;
  }
  .complete__btn {
    font-size: 2.2vw !important;
  }
  .type__img__one {
    border: 1px solid #f7f7f7 !important;
     padding: 0.52vw 12.56vw 0.52vw 1.56vw;
  }
}
</style>