<template>
  <hr />
  <section class="footer">
    <div class="footer__counts">
      <div class="footer__numbersCont">
        <span class="footer__underNum"> Открытых кейсов </span>
        <span class="footer__number">
          {{ currentlyOpened }}
        </span>
      </div>
      <div class="footer__numbersCont">
        <span class="footer__underNum"> Всего пользователей </span>
        <span class="footer__number">
          {{ usersAll }}
        </span>
      </div>
      <div class="footer__numbersCont">
        <span class="footer__underNum"> онлайн сейчас </span>
        <span class="footer__number">
          {{ usersOnline }}
        </span>
      </div>
    </div>
    <hr />
    <div class="footer_navigation">
      <img src="@/assets/img/foterlog.svg" style="width: 10.94vw" alt="" />
      <the-navbar></the-navbar>
      <a href="/PrivacyPolicy" class="privacy">Политика конфиденциальности</a>
      <a href="TermsOfUse" class="privacy">Пользовательское соглашение</a>
    </div>
    <hr />
    <div class="copyright">
      <p class="copyright__text">© 2018-2022 CS-MARKET</p>
      <p class="copyright__text">ТОО “CS-Market.kz”, г. Алматы, Аксай 2, 39</p>
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
  font-size:0.94vw;
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
  background-color: #060810;
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
  .copyright__text{
    font-size: 2vw;
  }
  .footer_navigation img{
    width:20vw  !important;
  }
  .privacy{
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