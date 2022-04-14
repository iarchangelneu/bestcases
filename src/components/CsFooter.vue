<template>
  <section class="footer">
    <div class="footer__counts">
      <img src="@/assets/img/qiwi.svg" style="width: 11.67vw" alt="" />
      <img src="@/assets/img/visa.svg" style="width: 9.53vw" alt="" />
      <img src="@/assets/img/master.svg" style="width: 5.94vw" alt="" />
      <img src="@/assets/img/wm.svg" style="width: 13.91vw" alt="" />
    </div>

    <div class="footer_navigation">
      <img src="@/assets/img/footerlogo.svg" style="width: 7.76vw" alt="" />
      <the-navbar></the-navbar>
      <a href="/privacy" class="privacy">Политика конфиденциальности</a>
      <a href="/terms" class="privacy">Пользовательское соглашение</a>
      <button class="steam__footer">Войти через Steam</button>
    </div>
    <div class="copyright">
      <p class="copyright__text">© 2018-2022 BestCases</p>
      <p class="copyright__text">ТОО “BestCases.kz”, г. Алматы, Аксай 2, 39</p>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {};
  },
  computed: {
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
.steam__footer {
  padding: 0.94vw 2.6vw 0.94vw 2.6vw;
  border: 0;
  color: #fff;
  font-weight: 400;
  font-size: 1.04vw;
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24;
  box-sizing: border-box;
  border-radius: 5px;
  -webkit-clip-path: polygon(0 10%, 100% 0, 100% -90%, 0 100%);
  clip-path: polygon(10% 0, 0 100%, 90% 100%, 100% 0);
}
.copyright__text {
  font-weight: 400;
  font-size: 1.25vw;
  color: rgba(255, 255, 255, 0.3);
  font-family: "Roboto";
}
.copyright {
  display: flex;
  justify-content: space-between;
  padding-left: 5.21vw;
  padding-right: 5.21vw;
  padding-top: 2.6vw;
  padding-bottom: 2.6vw;
}
.privacy {
  color: #fff;
  font-weight: 400;
  font-size: 0.94vw;
}
.footer_navigation {
  display: flex;
  padding-left: 5.21vw;
  padding-right: 5.21vw;
  padding-top: 2.6vw;
  padding-bottom: 2.6vw;
  justify-content: space-between;
  align-items: center;
}
.footer__counts {
  background: #1a1814;
  padding-top: 2.21vw;
  padding-bottom: 5.21vw;
  padding-left: 15.63vw;
  padding-right: 15.63vw;
  display: flex;
  justify-content: space-between;
}
hr {
  border: 1px solid rgba(255, 255, 255, 0.1);
}
.footer__ska {
  padding-top: 7vw;
}
.footer__navl {
  padding-left: 4vw;
  width: 5.21vw;
}
.footer__bar {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: 0;
}
.footer__padding {
  padding-top: 2.5vw;
  padding-left: 3.65vw;
}
.tt {
  position: absolute;
  bottom: 0;
  right: 0;
}
.heart__flex {
  padding-left: 15vw;
  display: flex;
  padding-bottom: 2.5vw;
}
.footer__flex {
  display: flex;
}
.footer {
  margin-top: 5.2vw;
  background-color: #141416;;
}
.ak47 {
  justify-content: center;
}
.ak47 img {
  width: 8.854vw;
}

/* numbers */

.footer__numbersFirst {
  position: relative;
  margin-left: 28.3vw;
  width: 70.21vw;
  background: #1f1f23;
  border-radius: 50px 0px 0px 50px;
  color: white;
  /* align-items: center;
  justify-content: space-around; */
}
.footer__numbersCont {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.footer__numbersCont span {
  text-align: center;
}
.footer__number {
  color: #fff;
  font-size: 3.65vw;
  font-weight: 900;
}
.footer__underNum {
  color: #2c6df5;
  font-size: 1.25vw;
  font-weight: 500;
  text-transform: uppercase;
}

.footer__logo {
  width: 20.31vw;
}

/* NAV */
.footer__nav {
  margin-top: 5.208vw;
}
.navbar {
  justify-content: center;
}

/* LINKS */
.footer__links {
  margin-top: 2.031vw;
}
.footer__links a {
  color: #ffffff;
  font-style: italic;
  text-decoration: underline;
  font-size: 1.25vw;
}

/* ADRESS */
.adress {
  margin-top: 3.125vw;
  color: #ffffff;
  text-align: center;
  font-size: 1.042vw;
}

@media screen and (max-width: 480px) {
  .copyright__text {
    font-size: 2vw;
  }
  .footer_navigation img {
    width: 20vw !important;
  }
  .privacy {
    font-size: 1.72vw;
    margin-right: 2vw;
  }
  .footer__navl {
    padding-left: 0;
    width: 5.21vw;
  }
  .ak47 img,
  .footer__logo {
    width: 20vw;
  }
  .footer__number {
    font-size: 5.3vw;
  }
  .footer__underNum {
    font-size: 2.875vw;
  }
  .footer__links a {
    font-size: 2.25vw;
  }
  .adress {
    font-size: 2vw;
  }
  .footer__numbersFirst {
    background: unset;
    margin-left: 15vw;
  }
  .footer__flex {
    align-items: flex-start;
  }
}
</style>