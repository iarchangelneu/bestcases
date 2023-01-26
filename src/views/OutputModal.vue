<template>
  <div class="modal fade" id="OutputMoney" tabindex="-1" aria-labelledby="OutputMoney" aria-hidden="true">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <div class="money__main text-center">
            <p>Вывод средств</p>

            <div class="typebuttons d-flex justify-content-center">
              <button class="outBtn" @click="openOutModal()">ПОПОЛНИТЬ БАЛАНС</button>
              <button class="inBtn btn__active">ВЫВОД СРЕДСТВ</button>
            </div>
          </div>
        </div>
        <div class="modal-body">
          <div class="modalbody">
            <h2>Порядок действий для вывода средств</h2>

            <p class="mt-3">1. Выберите метод вывода:</p>

            <div class="typesradio mt-4">
              <div class="d-flex align-items-center mb-4">
                <input type="radio" name="Type" id="cardType2">
                <label for="cardType">Банковская карта</label>
              </div>
              <div class="d-flex align-items-center">
                <input type="radio" name="Type" id="telType2">
                <label for="telType">Баланс мобильного телефона</label>
                <input type="text" name="tel" id="tel" class="telInp">
              </div>
            </div>


            <p class="mt-4">2. Подтвердите Ваше согласие с правилами нашей системы</p>

            <div class="privacycheck d-flex align-items-center mt-4">

              <input type="checkbox" name="privacy" id="privacy">

              <label for="privacy">Я согласен с <a href="/terms">пользовательским соглашением</a> и <a
                  href="/privacy">политикой конфиденциальности</a> </label>

            </div>

            <p class="mt-4">3. Введите сумму, на которую Вы хотите пополнить личный счет, и нажмите на кнопку
              “Пополнить”. Вы будете переадресованы на сайт платежной системы, где сможете завершить платеж.</p>
          </div>
        </div>

        <div class="modalfooter">
          <div class="payzone d-flex justify-content-between align-items-center">
            <input type="number" name="paySum" id="paySum" v-model="outSum" placeholder="500 ₸">
            <button id="inButton" @click="phoneOut()">
              <div class="spinner-border text-info inSpinner" role="status">
                <span class="sr-only">Loading...</span>
              </div>
              <span id="buttonText2">ВЫВЕСТИ</span>
            </button>
          </div>

          <div class="pickSum d-flex align-items-center justify-content-between pt-4 pb-4">
            <button @click="outSum = 500" :class="[{ 'sumActive': outSum == 500 }]">500 ₸</button>
            <button @click="outSum = 1000" :class="[{ 'sumActive': outSum == 1000 }]">1000 ₸</button>
            <button @click="outSum = 2000" :class="[{ 'sumActive': outSum == 2000 }]">2000 ₸</button>
            <button @click="outSum = 5000" :class="[{ 'sumActive': outSum == 5000 }]">5000 ₸</button>
            <button @click="outSum = 10000" :class="[{ 'sumActive': outSum == 10000 }]">10000 ₸</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import IMask from 'imask';
import axios from 'axios';

export default {
  data() {
    return {
      payment: "",
      outSum: null,
      isIn: 1,
      ip: null,
    };
  },
  methods: {
    openOutModal() {
      $("#OutputMoney").modal("hide");
      $("#Money").modal("show");
    },

    phoneOut() {
      let card = document.querySelector('#cardType2')
      let phone = document.querySelector('#telType2')
      let number = document.querySelector('#tel')
      let span = document.querySelector('#buttonText2')
      let spin = document.querySelector('.inSpinner')
      let button = document.querySelector('#inButton')

      if (card.checked == false && phone.checked == false) {
        alert("Выберите способ оплаты")
      }

      else if (this.outSum >= 500 && card.checked == true) {
        var token = localStorage.getItem('userName')
        axios
          .post('https://bestcases.kz/api/vision_return/', { cost: this.outSum, jwt_token: token })
          .then((res) => {
            console.log(res)
            window.location.href = res.data.url

          })
          .catch((error) => {
            console.error(error);
            console.log('Успех')
          });
        span.style.display = 'None'
        button.disabled = true
        spin.classList.add('outSpinnerActive')

        setTimeout(() => {
          span.style.display = 'block'
          button.disabled = false
          spin.classList.remove('outSpinnerActive')
        }, 30000);


      }
      else if (this.outSum >= 500 && phone.checked == true) {

        if (number.value) {
          var token = localStorage.getItem('userName')
          axios
            .post('https://bestcases.kz/api/vision_mobile_return/', { cost: this.outSum, jwt_token: token, phone: number.value })
            .then((res) => {

              span.style.display = 'None'
              button.disabled = true
              spin.classList.add('outSpinnerActive')

              setTimeout(() => {
                span.style.display = 'block'
                button.disabled = false
                spin.classList.remove('outSpinnerActive')
              }, 30000);

              console.log(res)
              window.location.href = res.data.url


            })
            .catch((error) => {
              console.error(error);
            })

        }
        else {
          alert("Укажите номер телефона")
        }



      }
      else {
        alert('Сумма должна быть ни меньше 500')
      }
    },

  },
  mounted() {
    var phoneMask = IMask(
      document.getElementById('tel'), {
      mask: '+70000000000'
    });
  }
};
</script>

<style scoped>
.modal-content {
  border: 3px solid rgba(234, 196, 139, 0.5);
}

.outSpinnerActive {
  display: block !important;
}

.inSpinner {
  display: none;
}

.sumActive {
  background: linear-gradient(235.92deg, #753EF9 14.85%, #9D75FF 87.62%) !important;
  border: 0 !important;
  transition: all .3s ease;
}

.pickSum button {
  padding: 12px 20px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 5px;
  border: 2px solid #EAC48B;

  font-family: 'Exo', sans-serif;
  font-style: normal;
  font-weight: 500;
  font-size: 18px;
  line-height: 24px;
  color: #FFFFFF;
  transition: all .3s ease;
}


.telInp {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 5px;
  border: 1px solid #EAC48B;
  font-family: 'Exo', sans-serif;
  font-style: normal;
  font-weight: 500;
  font-size: 20px;
  line-height: 37px;
  text-align: left;
  color: #fff;
  margin-left: 16px;
  width: 40% !important;
}

.payzone button {
  background: #F15A24;
  border-radius: 5px;
  padding: 16px 73px;
  border: 0;

  font-family: 'Exo', sans-serif;
  font-style: normal;
  font-weight: 500;
  font-size: 20px;
  line-height: 27px;
  transition: all .3s ease;
  /* identical to box height */


  color: #FFFFFF;

}

.payzone input {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 5px;
  border: 2px solid #EAC48B;
  font-family: 'Exo', sans-serif;
  font-style: normal;
  font-weight: 500;
  font-size: 28px;
  line-height: 37px;
  text-align: right;
  height: 59px;

  color: #FFFFFF;
}

.modalfooter {
  padding: 0 50px;
}

.privacycheck a {
  text-decoration: underline;
  font-family: 'Exo', sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 21px;
  color: #FFFFFF;
}

.privacycheck label {
  font-family: 'Exo', sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 21px;
  color: #FFFFFF;
  margin-left: 20px;
  margin-bottom: 0;
}

.privacycheck input {
  width: 20px;
  height: 20px;
}

.typesradio input {
  width: 25px;
  height: 25px;
}

.typesradio label {
  font-family: 'Exo', sans-serif;
  font-style: normal;
  font-weight: 500;
  font-size: 20px;
  line-height: 27px;
  color: #FFFFFF;
  margin-bottom: 0;
  margin-left: 16px;
}

.modalbody p {
  font-family: 'Exo', sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 21px;

  color: #FFFFFF;
}

.modalbody {
  padding: 0 35px;
}

h2 {
  font-family: 'Exo', sans-serif;
  font-style: normal;
  font-weight: 600;
  font-size: 20px;
  line-height: 27px;
  color: #FFFFFF;
}

.outBtn {
  background: transparent;
  border-radius: 10px;
  padding: 12px 42px;
  border: 1px solid rgba(234, 196, 139, 0.5);
  border-top-left-radius: 0;
  border-bottom-left-radius: 0;
  border-left: 0;
  width: 100%;


  font-weight: 500;
  font-size: 16px;
  line-height: 21px;
  font-family: 'Exo', sans-serif;
  color: #fff;
}

.inBtn {
  background: #EAC48B;
  ;
  border-radius: 10px;
  padding: 12px 42px;
  border: 0;
  width: 100%;


  font-weight: 500;
  font-size: 16px;
  line-height: 21px;
  font-family: 'Exo', sans-serif;
  color: #fff;
}

.money__main p {
  color: #fff;
  font-weight: 700;
  font-size: 24px;
  line-height: 32px;
}

.money__main {
  padding: 20px 50px;
}

.modal-dialog {
  width: 100% !important;
  min-width: 40% !important;
}

@media (max-width: 1440px) {
  .payzone input {
    width: 180px;
  }

  .pickSum button {
    padding: 12px 10px;
  }

  .outBtn,
  .inBtn {
    padding: 12px 15px;
  }
}

@media (max-width: 1366px) {
  .payzone button {
    padding: 16px 43px;
  }
}

@media (max-width: 1024px) {
  h2 {
    font-size: 16px;
  }

  .typesradio label {
    font-size: 16px;
  }

  .inBtn,
  .outBtn {
    font-size: 14px;
  }

  .pickSum button {
    font-size: 14px;
  }

  .payzone button {
    font-size: 16px;
  }

  @media (max-width: 480px) {
    .money__main {
      padding: 20px 20px;
    }

    .modalbody {
      padding: 0 5px;
    }

    .modalfooter {
      padding: 0 20px;
    }

    .privacycheck label,
    .modalbody p,
    .typesradio label {
      font-size: 14px;
    }

    .payzone button {
      padding: 16px 34px;
    }

    .privacycheck input {
      width: 50px;
      height: 50px;
    }
  }

  @media (max-width: 390px) {

    .outBtn,
    .inBtn {
      padding: 12px 0px;
    }

    h2 {
      font-size: 14px;
    }

    .payzone input {
      width: 140px;
    }

    .payzone button {
      padding: 16px 20px;
    }

    .pickSum button {
      padding: 0px 7px;
    }

    .pickSum button {
      font-size: 12px;
    }
  }

  @media (max-width: 320px) {
    .payzone input {
      width: 107px;
    }

    .pickSum button {
      padding: 0px 1px;
    }
  }
}
</style>