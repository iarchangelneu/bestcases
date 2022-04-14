<template>
  <div class="container-fluid cases_page">
    <div class="row">
      <div class="col-12" style="padding-top: 40px;">
        <div class="casses__section">
          <span class="casses__title">
            <img src="../assets/img/SalesCases.png" alt="">
          </span>
          <div class="casses__row">
            <div class="casses__card">
              <div class="cases__sale">
                -5%
              </div>
              <img src="../assets/img/casesDeagle.png" alt="" class="casses__img">
              <div class="card__footer">
                <div class="casses__name">
                Desert Eagle
                </div>
                <div class="casses__btn">
                  <span>от</span>&nbsp; 5 690 ₸
                </div>
              </div>
            </div>

            <div class="casses__card">
              <div class="cases__sale">
                -10%
              </div>
              <img src="../assets/img/casesAwp.png" alt="" class="casses__img">
              <div class="card__footer">
                <div class="casses__name">
                AWP
                </div>
                <div class="casses__btn">
                  <span>от</span>&nbsp; 15 990 ₸
                </div>
              </div>
            </div>

            <div class="casses__card">
              <div class="cases__sale">
                -15%
              </div>
              <img src="../assets/img/casesKnife.png" alt="" class="casses__img">
              <div class="card__footer">
                <div class="casses__name">
                Bowie Knife
                </div>
                <div class="casses__btn">
                  <span>от</span>&nbsp; 200 590 ₸
                </div>
              </div>
            </div>

            <div class="casses__card">
              <div class="cases__sale">
                -5%
              </div>
              <img src="../assets/img/casesRev.png" alt="" class="casses__img">
              <div class="card__footer">
                <div class="casses__name">
                R8 Revolver
                </div>
                <div class="casses__btn">
                  <span>от</span>&nbsp; 7 390 ₸
                </div>
              </div>
            </div>

            <div class="casses__card">
              <div class="cases__sale">
                -10%
              </div>
              <img src="../assets/img/casesPistol.png" alt="" class="casses__img">
              <div class="card__footer">
                <div class="casses__name">
                Glock-18
                </div>
                <div class="casses__btn">
                  <span>от</span>&nbsp; 3 590 ₸
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="casses__section">
          <span class="casses__title">
            <img src="../assets/img/PopularCases.png" alt="">
          </span>
          <div class="casses__row">
            <div class="casses__card">
              <img src="../assets/img/GammaCase.png" alt="" class="casses__img">
              <div class="card__footer">
                <div class="casses__name">
                Кейс “Gamma”
                </div>
                <div class="casses__btn">
                  <span>от</span>&nbsp; 5 690 ₸
                </div>
              </div>
            </div>

            <div class="casses__card">
              <img src="../assets/img/RestrictedCase.png" alt="" class="casses__img">
              <div class="card__footer">
                <div class="casses__name">
                Кейс “Restricted”
                </div>
                <div class="casses__btn">
                  <span>от</span>&nbsp; 15 990 ₸
                </div>
              </div>
            </div>

            <div class="casses__card">
              <img src="../assets/img/InfernoCase.png" alt="" class="casses__img">
              <div class="card__footer">
                <div class="casses__name">
                Кейс “Inferno”
                </div>
                <div class="casses__btn">
                  <span>от</span>&nbsp; 200 590 ₸
                </div>
              </div>
            </div>

            <div class="casses__card">
              <img src="../assets/img/BravoCase.png" alt="" class="casses__img">
              <div class="card__footer">
                <div class="casses__name">
                Кейс “Bravo”
                </div>
                <div class="casses__btn">
                  <span>от</span>&nbsp; 7 390 ₸
                </div>
              </div>
            </div>

            <div class="casses__card">
              <img src="../assets/img/RevolverCase.png" alt="" class="casses__img">
              <div class="card__footer">
                <div class="casses__name">
                Кейс “Revolver”
                </div>
                <div class="casses__btn">
                  <span>от</span>&nbsp; 3 590 ₸
                </div>
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
  data() {
    return {
      cases: [
        
      ],
      newcases:[],
      salecases: [
        
      ],
      activeTab: "Classik",
    };
  },
  methods: {
     getCases() {
      const path = "https://realcases.kz/api/cases";
      axios
        .get(path)
        .then((res) => {
          // for(let i=31; i<36;i++){
          //     this.newcases.push(res.data[i])
          // }
          // for(let i=91; i<96;i++){
          //     this.cases.push(res.data[i])
          // }
          // for(let i=51; i<56;i++){
          //     this.salecases.push(res.data[i])
          // }
          // this.cases = res.data;
          console.log(res);
          console.log(this.cases);
        })
        .catch((error) => {
          console.error(error);
        });
    },
    classicPrev() {
      $(".sliderClassik").slick("slickPrev");
    },
    classicNext() {
      $(".sliderClassik").slick("slickNext");
    },
    rarePrev() {
      $(".rarItems").slick("slickPrev");
    },
    rareNext() {
      $(".rarItems").slick("slickNext");
    },
  },
  mounted() {
    $(".rarItems").slick({
      centerMode: true,
      infinite: true,
      slidesToShow: 3,
      // autoplay: true,
      arrows: false,
      responsive: [
        {
          breakpoint: 480,
          settings: {
            slidesToShow: 1,
          },
        },
      ],
    });
    this.getCases();
     $(".live").slick({
      infinite: true,
      slidesToShow: 9,
      slidesToScroll: 1,
      autoplay: true,
      arrows: false,
      draggable: false,
      vertical: true,
      responsive: [
        {
          breakpoint: 480,
          settings: {
            slidesToShow: 6,
          },
        },
      ],
    });
  },
  
};
</script>

<style scoped>
.cases__sale{
  background: rgba(241, 90, 36, 0.4);  
  border: 1px solid #F15A24;
  padding: 4px 8px;
  margin-left: auto;
  margin-right: 10px;
  border-radius: 5px;
}
.casses__btn span{
  font-size: 1.042vw;
  color: rgba(255, 255, 255, 0.3);
}







.cases_page{
  background-color: #1A1814;
  /* background: no-repeat right/80% url(@/assets/img/SolderBack.png) #141721; */
  padding-bottom: 20px;
}

.casses__section{
  margin-top: 4.167vw;
}
.casses__title{
  font-weight: 900;
  font-size: 1.667vw;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
}
.casses__row{
  display: flex;
  justify-content: space-between;
  margin-top: 2.604vw;
}
.casses__card{
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.casses__img{
  width: 14.323vw;
}
.casses__name{
  font-weight: 900;
  font-size: 1.146vw;
  margin-top: 2.204vw;
}
.casses__btn{
  font-size: 1.250vw;
  color: white;
  margin-top: 0.304vw;
  font-weight: 400;
}
/* LIVE */
.live__card{
  width: 80%;
  padding-top: 1.042vw;
  display: flex;
  flex-direction: column;
  background: radial-gradient(#1E1D21, #3C3B3F);
  border-left: 4px solid #2C6DF5;
}
.live__img{
  width: 7.240vw;
  margin-left: auto;
  margin-right: auto;
}
.live__bottom{
  padding-left: 14px;
  padding-right: 14px;
}
.live__bottomgroup{
  display: flex;
  justify-content: space-between;
}
.live__name{
  color: white;
  font-size: 1.042vw;
  font-weight: 900;
}
.live__quality{
  color: #FFFFFF4D;
  font-size: 1.042vw;
}
.live__price{
  font-weight: 700;
  font-size: 1.042vw;
  color: #2C6DF5;
}

</style>