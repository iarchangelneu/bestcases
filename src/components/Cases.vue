<template>
  <div class="container-fluid cases_page">
    <div class="row">
      <div class="col-2 pl-0">
        <div class="livecont">
          <div class="live">
            
            <div v-for="live in 20" :key="live">
              <div class="live__card">
                <img src="@/assets/img/livepistol.png" alt="" class="live__img">
                <div class="live__bottom">
                  <div class="live__bottomgroup">
                    <div class="live__name">
                      Pistol      
                    </div>
                    <div class="live__quality">
                      FN
                    </div>
                  </div>
                  <div class="live__price">
                    1000 ₸
                  </div>
                </div>
              </div>
            </div>
            
          </div>
        </div>
      </div>
      <div class="col-10" style="padding-top: 40px;">
        <div class="casses__section">
          <div class="casses__title">
            Популярные кейсы
          </div>
          <div class="casses__row">
            <div class="casses__card" v-for="cases in salecases" :key="cases">
              <img src="@/assets/img/casesRar5.png" alt="" class="casses__img">
              <div class="casses__name">
                {{cases.name}}
              </div>
              <button class="casses__btn btn">
                {{Math.floor(cases.cost)}} ₸
              </button>
            </div>
          </div>
        </div>

        <div class="casses__section">
          <div class="casses__title">
            Лучшие предметы
          </div>
          <div class="casses__row">
            <div class="casses__card" v-for="cases in cases" :key="cases">
              <img src="@/assets/img/casesRar5.png" alt="" class="casses__img">
              <div class="casses__name">
                {{cases.name}}
              </div>
              <button class="casses__btn btn">
                {{Math.floor(cases.cost)}} ₸
              </button>
            </div>
          </div>
        </div>

        <div class="casses__section">
          <div class="casses__title">
            Скидки и новинки
          </div>
          <div class="casses__row">
            <div class="casses__card" v-for="cases in newcases" :key="cases">
              <img src="@/assets/img/casesRar5.png" alt="" class="casses__img">
              <div class="casses__name">
                {{cases.name}}
              </div>
              <button class="casses__btn btn">
                {{Math.floor(cases.cost)}} ₸
              </button>
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
      cases: [],
      newcases:[],
      salecases: [],
      activeTab: "Classik",
    };
  },
  methods: {
     getCases() {
      const path = "https://realcases.kz/api/cases";
      axios
        .get(path)
        .then((res) => {
          for(let i=31; i<35;i++){
              this.newcases.push(res.data[i])
          }
          for(let i=91; i<95;i++){
              this.cases.push(res.data[i])
          }
          for(let i=51; i<55;i++){
              this.salecases.push(res.data[i])
          }
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
.cases_page{
  background-color: #141721;
  background: no-repeat right/80% url(@/assets/img/SolderBack.png) #141721;
  padding-bottom: 20px;
}

.casses__section{
  margin-top: 4.167vw;
}
.casses__title{
  font-weight: 900;
  font-size: 1.667vw;
  color: white;
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
  align-items: center;
}
.casses__img{
  width: 14.323vw;
}
.casses__name{
  font-weight: 400;
  font-size: 1.250vw;
  margin-top: 2.204vw;
}
.casses__btn{
  font-size: 1.250vw;
  background-color: #2C6DF5;
  padding: 0.625vw 2.604vw;
  color: white;
  margin-top: 1.304vw;
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