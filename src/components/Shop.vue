<template>
    <section class="shop">

        <div class="container-fluid cont__pd">
            
                <div class="row">
                <div class="col-md-3 col-12">
                    <div class="d-flex catalog__topfilters">
                        <!-- <div class="d-flex align-items-center reloadsort">
                            <img src="@/assets/img/reloadCatalog.png" class="catalog__reloadImg" alt="" @click="reloadCatalog">
                            <img src="@/assets/img/catalogLine.png" class="catalog__lineImg" alt="">
                            <div class="dropdown">
                                <button 
                                class="btn dropdown-toggle dropdown__catalog" 
                                type="button" 
                                id="dropdownMenuButton" 
                                data-toggle="dropdown" 
                                aria-haspopup="true" 
                                aria-expanded="false">
                                    {{sort}}
                                    <img src="@/assets/img/catalogArrow.png" class="catalog__ArrowImg" alt="">
                                </button>
                                <div class="dropdown-menu catalog__dropmenu" aria-labelledby="dropdownMenuButton">
                                    <a class="dropdown-item catalog__dropitem" href="#" @click="this.sort='По умолчанию'">По умолчанию</a>
                                    <a class="dropdown-item catalog__dropitem" style="border-top: 1px solid white; border-bottom: 1px solid white;" href="#" @click="this.sort='По цене (Max)'">По цене (Max)</a>
                                    <a class="dropdown-item catalog__dropitem" href="#" @click="this.sort='По цене (Min)'">По цене (Min)</a>
                                </div>
                            </div>
                        </div> -->
                        
                        <input type="text" class="catalog__search" placeholder="Поиск по товарам" v-model.trim="search">

                        <div class="filtcontm">
                                <span class="filters__spans">Редкость</span>
                                <div class="dropdown">
                                    <button class="btn dropdown-toggle dropdown__filters" type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                                        {{rarityList[rareSelect].rare}}
                                        <img src="@/assets/img/catalogArrowM.png" class="catalog__ArrowImg" alt="">
                                    </button>
                                    <div class="dropdown-menu catalog__dropmenu " aria-labelledby="dropdownMenuButton">
                                        <a  
                                        href="#"
                                        v-for="rarity in rarityList" 
                                        :key="rarity.id"
                                        :class="['dropdown-item', 'catalog__dropitem', {'catalog__dropitemBorder': rarity.id !=5}, {'active': rarity.id == this.rareSelect}]"
                                        @click="this.rareSelect = rarity.id"
                                        >
                                        {{rarity.rare}}
                                        </a>
                                    </div>
                                </div>
                            </div>

                            <div class="filtcontm">
                                <span class="filters__spans">Состояние</span>
                                <div class="dropdown">
                                    <button class="btn dropdown-toggle dropdown__filters" type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                                        {{conditionList[conditionSelect].cond}}
                                        <img src="@/assets/img/catalogArrowM.png" class="catalog__ArrowImg" alt="">
                                    </button>
                                    <div class="dropdown-menu catalog__dropmenu" aria-labelledby="dropdownMenuButton">
                                        <a 
                                        class="dropdown-item catalog__dropitem" 
                                        v-for="condition in conditionList" 
                                        :key="condition.id"
                                        @click="this.conditionSelect = condition.id"
                                        :class="['dropdown-item', 'catalog__dropitem', {'catalog__dropitemBorder': condition.id !=5}, {'active': condition.id == this.conditionSelect}]"
                                        >
                                        {{condition.cond}}
                                        </a>
                                    </div>
                                </div>
                            </div>

                            <div class="prices__container">
                                <span class="filters__spans">Цена</span>
                                <div class="filter__prices">
                                    <input type="number" class="price__min" placeholder="от 0.00" v-model.trim="lowprice">
                                    <span class="ml-2 mr-2">&mdash;</span>
                                    <input type="number" class="price__max" placeholder="до 0.00" v-model.trim="highprice">
                                </div>
                            </div>

                            <button class="btn filter__button">
                                Применить фильтр
                            </button>
                            
                        
                        
                    </div>    
                </div>

                <div class="col-12 col-md-9">
                    <div class="preshop-container">
                <div class="shop-container">
                <div class="row filtersAndCatalog">
                    <div class="col-12 col-md-12 catalog">
                        <!-- <div class="row"> -->
                            <!-- <div class="col-2" > -->
                                <div class="item" v-for="item in pageWeaponsList" :key="item.id" @click="openModal(item._id['$oid'])">
                                    <div class="item__top">
                                        <div class="d-flex flex-column">
                                            <div class="item__rare">
                                                {{item.rarity}}
                                            </div>
                                            
                                        </div>
                                        
                                    </div>
                                    <img :src="'/data/'+item.item_model_id" class="item__img" alt="">
                                    <div class="item__bottomcont">
                                        <div class="item__bottom">
                                            <span class="item__name">
                                                {{item.full_type}}
                                            </span>
                                            <div>
                                                {{item.quality}}
                                            </div>
                                        </div>
                                        <span class="item__price">
                                            {{Math.floor(item.cost)}} ₸
                                        </span>
                                    </div>
                                </div>
                            <!-- </div> -->
                        <!-- </div> -->
                    </div>
                </div>
            </div>
            <div class="col-12 pagination__precont">
            <div class="pagination__cont">
                <button class="pagination__prev" @click="prevPage">
                    Назад
                </button>
                <div class="pagination__numbers">
                    {{this.pageNumber}} / {{this.MaxPages}}
                </div>
                <button class="pagination__next" @click="nextPage">
                    Вперед
                </button>
            </div>
            </div>
            </div>
                </div>
            
            </div>
            
        </div>
        

        <div class="container-fluid cont__pd mt-4">
            
            
        </div>

        <div class="container-fluid cont__pd mt-4">
            
        </div>
    </section>   
    <product-modal
    :product="modal.modalProductName"
    ></product-modal> 
</template>

<script>
import ProductModal from '@/components/ProductModal.vue';
export default {
    data(){
        return {
            pokemons: [],
            modal: {
                modalProductName: {},
            },
            sort: 'По умолчанию',
            rarityList:[
                {id: 0, rare: 'Любое'},
                {id: 1, rare: 'Армейское качество'},
                {id: 2, rare: 'Запрещённое'},
                {id: 3, rare: 'Засекреченное'},
                {id: 4, rare: 'Тайное'},
                {id: 5, rare: 'Экстра'},
            ],
            conditionList:[
                {id: 0, cond: 'Любое', short: 'All'},
                {id: 1, cond: 'Factory New', short: 'FN', float: 0},
                {id: 2, cond: 'Minimal Wear', short: 'MW', float: 0.2},
                {id: 3, cond: 'Field-Tested', short: 'FT', float: 0.4},
                {id: 4, cond: 'Well-Worn', short: 'WW', float: 0.6},
                {id: 5, cond: 'Battle-Scarred', short: 'BS', float: 0.8},
            ],
            pageNumber: 1,
            weapons: [],
            // weapons: [
            //     {
            //         id: 0,
            //         img: require('../assets/img/cataloitem_1.png'),
            //         rarity: 'Армейское',
            //         name: 'Karambit',
            //         pattern: 908,
            //         price: 1000,
            //         float: 0.5,
            //         collection: 'Red',
            //     },
            //     {
            //         id: 1,
            //         img: require('../assets/img/tacti__cart.png'),
            //         rarity: 'Запрещенное',
            //         name: 'AK-47',
            //         pattern: 908,
            //         price: 2500,
            //         float: 0.3,
            //         collection: 'Red-Line',
            //     },
            //     {
            //         id: 2,
            //         img: require('../assets/img/voi__cart.png'),
            //         rarity: 'Засекреченное',
            //         name: 'USP',
            //         pattern: 908,
            //         price: 7000,
            //         float: 0.7,
            //         collection: 'Dark',
            //     },
            //     {
            //         id: 3,
            //         img: require('../assets/img/cataloitem_1.png'),
            //         rarity: 'Тайное',
            //         name: 'AWP',
            //         pattern: 908,
            //         price: 25000,
            //         float: 0.79,
            //         collection: 'Dragon Lore',
            //     },
            //     {
            //         id: 4,
            //         img: require('../assets/img/cataloitem_1.png'),
            //         rarity: 'Армейское',
            //         name: 'Karambit',
            //         pattern: 908,
            //         price: 55000,
            //         float: 0.1,
            //         collection: 'Red',
            //     },
            //     {
            //         id: 5,
            //         img: require('../assets/img/cataloitem_1.png'),
            //         rarity: 'Запрещенное',
            //         name: 'AK-47',
            //         pattern: 908,
            //         price: 35000,
            //         float: 0.2,
            //         collection: 'Red-Line',
            //     },
            //     {
            //         id: 6,
            //         img: require('../assets/img/cataloitem_1.png'),
            //         rarity: 'Засекреченное',
            //         name: 'USP',
            //         pattern: 908,
            //         price: 255000,
            //         float: 0.45,
            //         collection: 'Dark',
            //     },
            //     {
            //         id: 7,
            //         img: require('../assets/img/cataloitem_1.png'),
            //         rarity: 'Тайное',
            //         name: 'AWP',
            //         pattern: 908,
            //         price: 152487,
            //         float: 0.14,
            //         collection: 'Dragon Lore',
            //     },
            //     {
            //         id: 8,
            //         img: require('../assets/img/cataloitem_1.png'),
            //         rarity: 'Тайное',
            //         name: 'AWP',
            //         pattern: 908,
            //         price: 16000,
            //         float: 0.34,
            //         collection: 'Dragon Lore',

            //     },
                
                
            // ],
            search: '',
            lowprice: '',
            highprice: '',
            rareSelect: 0,
            conditionSelect: 0,
        }
    },
    
    methods:{
        getData(){
            const path = 'https://realcases.kz/api/shop';
            axios.get(path)
                .then((res) => {
                    this.weapons = res.data;
                console.log(res.data[0]);
                })
                .catch((error) => {
                // eslint-выключение следующей строки
                console.error(error);
                });
        },
        openModal(id){
            // console.log(this.weapons.filter(item => item.id == id)[0].name)
            this.modal.modalProductName = this.weapons.filter(item => item._id['$oid'] == id)[0];
            $('#ProductModal').modal('show')
        },
        reloadCatalog(){
            this.search = '';
            this.lowprice = '';
            this.highprice = ''
            this.rareSelect = 0;
            this.conditionSelect = 0;
            this.sort = 'По умолчанию';
        },
        addRarity(id){
            this.rareSelect.push(id)
        },
        removeRarity(id){
            this.rareSelect.splice(this.rareSelect.indexOf(id),1)
            console.log(this.rareSelect) 
        },
        nextPage(){
            if(this.pageNumber < this.filteredWeapons.length/20){
                this.pageNumber = this.pageNumber + 1;
                // console.log(this.pageNumber)
            }
        },
        prevPage(){
            if(this.pageNumber > 1 ){
                this.pageNumber = this.pageNumber - 1;
                // console.log(this.pageNumber)
            }
        },
    },
    computed:{
        filteredWeapons(){
            let searched = this.weapons.filter((product) => {
                if(this.lowprice === ''){
                    return product.full_type.toLowerCase().indexOf(this.search.toLowerCase()) !== -1
                }
                else{
                    return product.full_type.toLowerCase().indexOf(this.search.toLowerCase()) !== -1 && product.cost>this.lowprice;
                }
            });
            if(this.highprice !== ''){
                searched = searched.filter((product) => {
                    return product.cost <= Number(this.highprice)    
                })
            };
            if(this.rareSelect != 0){
                searched = searched.filter(product => {
                    return product.rarity.toLowerCase() == (this.rarityList[this.rareSelect].rare.toLowerCase())    
                })
            }
            if(this.conditionSelect != 0){
                searched = searched.filter(product => {
                    return product.quality == (this.conditionList[this.conditionSelect].short)    
                })    
            }
            if(this.sort==='По цене (Min)'){
                searched.sort((a,b)=>{
                    return a.cost - b.cost
                })    
            }
            if(this.sort==='По цене (Max)')
            {
                searched.sort((a,b)=>{
                    return b.cost - a.cost
                })    
            }

            // console.log(searched[0])
            

            return searched
            
        },
        pageWeaponsList(){
            if(this.filteredWeapons.length>0){
                let pageWeapons = [];
                let ind = 0;
                if (this.pageNumber > 1){
                    ind = (this.pageNumber-1)*20
                }
                for(let i = ind; i <= ind + 19 && i<this.filteredWeapons.length; i++){
                    pageWeapons.push(this.filteredWeapons[i])
                }
                console.log(pageWeapons)
                return pageWeapons;
        }
        },
        MaxPages(){
            return Math.ceil(this.filteredWeapons.length/20);
        }
    },
    mounted(){
        this.getData();
    },
    components:{ProductModal}
}
</script>

<style scoped>
.pagination__precont{
    background-color: #1A1814;
    padding: 1.875vw 16px;
    
}
.pagination__cont{
    display: flex;
    justify-content: space-between;
    background-color: #1E1D21;
    align-items: center;
    border-radius: 5px;
}
.pagination__prev{
    background-color: #1E1D21;
    border: 0;
    color: #FFFFFF;
    font-size: 1.250vw;
    padding: 20px;
    border-right: 1px solid rgba(255, 255, 255, 0.1);
}
.pagination__next{
    background-color: #1E1D21;
    border: 0;
    color: #FFFFFF;
    font-size: 1.250vw;
    padding: 20px;
    border-left: 1px solid rgba(255, 255, 255, 0.1);
}
.pagination__numbers{
    color: #FFFFFF;
    font-size: 1.250vw;
}


.cont__pd{
    padding-left: 5.208vw;
    padding-right: 5.208vw;
}
.filters__container{
    padding: 17px 24px;
    background: #2B2E37;
    border-radius: 5px;
    /* font-family: 'Roboto', sans-serif; */
}
    .shop{
        padding-top: 160px;
        /* background: no-repeat right/80% url(@/assets/img/SolderBack.png) #141721; */
        background-color: #1A1814;
    }
    .preshop-container{
        /* background: rgba(234, 196, 139, 0.5); */
        border-radius: 5px;
        /* padding: 1px; */
        border: 1px solid rgba(234, 196, 139, 0.5);
    }
    .shop-container{
        background-color: #1A1814;
        /* width: 96vw; */
        padding: 16px;
        /* border-radius: 5px; */
        /* margin-left: 30px; */
        /* margin-right: 30px; */
    }


    .catalog__reloadImg{
        width: 40px;  
        height: 40px;  
        cursor: pointer;
    }
    .catalog__lineImg{
        margin-left: 0.563vw;
        margin-right: 0.563vw;
    }
    .dropdown__catalog{
        color: white;
        font-weight: 500;
        font-size: 1.250vw;
        background-color: unset;
    }
    .dropdown__filters{
        /* margin-top: 15px; */
        color: #FFFFFF4D;
        font-weight: 400;
        font-size: 1.042vw;
        /* font-family: 'Roboto', sans-serif; */
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        border: 1px solid #1E1D21;
        
    }
    .dropdown__catalog::after{
        display: none;
    }
    .dropdown__filters::after{
        display: none;
    }
    .dropdown__filters:focus{
        box-shadow: 0 0 0 0.1rem #EAC48B;
    }
    .catalog__ArrowImg{
        width: 10px;
        margin-left: 16px;
    }
    .dropdown__catalog:focus{
        box-shadow: 0 0 0 0.2rem #3F7AF5;
    }
    .catalog__dropmenu{
        background-color: #332e24; 
        box-shadow: 0px 8px 8px 0px rgba(234, 196, 139, 0.2);
        color: white;   
        padding: 0;
    }
    .catalog__dropitem{
        color: white;
        font-size: 20px;
    }
    .catalog__dropitemBorder{
        border-bottom: 1px solid white;
    }
    .catalog__dropmenu .active{
        background-color: rgba(234, 196, 139, 0.2);
        color: rgba(255, 255, 255,0.5);
        /* border: 1px solid #753ef9; */
    }
    .catalog__dropitem:hover{
        color: white;
        font-size: 20px;
        background-color: #EAC48B;
        cursor: pointer;
    }
    .catalog__search{
        background-color: #171717;    
        border: 1px solid rgba(255, 255, 255, 0.1);
        background: url(@/assets/img/loopCatalogM.png) no-repeat 10px center;
        background-size: 1.250vw;
        color: white;
        padding-left: 45px;
        width: 20vw;
        height: 2.865vw;
        font-size: 24px;
        font-weight: 500;
        border-color: rgba(255, 255, 255, 0.1);
        border-radius: 5px;
        /* font-family: 'Roboto', sans-serif; */
    }
    .catalog__search::placeholder{
        color: rgba(255, 255, 255, 0.3);
        font-size: 24px;
        font-weight: 500;
    }


    /* FILTERS */
    .filtersAndCatalog{
        /* margin-top: 30px; */
        /* padding-bottom: 2.6vw;     */
    }
    
    .filters{
        color: white;
        font-weight: 600;
        font-size: 1.250vw;
    }
    .filter__prices{
        color: white;
        display: flex;
        align-items: center;
    }
    .prices__container{
        display: flex;
        /* align-items: center; */
        flex-direction: column;
    }
    .price__min{
        width: 8.917vw;
        height: 38px;
        font-weight: 500;
        font-size: 1.458vw;
        /* background-color: #171717; */
        border: 1px solid #EAC48B;
        background: url(@/assets/img/tenge.png) no-repeat right 5px center #1E1D21;
        padding-right: 30px;
        color: white;
        background-size: 0.563vw;

    }
    .price__max{
        width: 8.917vw;
        height: 38px;
        font-weight: 500;
        font-size: 1.458vw;
        /* background-color: #171717; */
        border: 1px solid #EAC48B;
        background: url(@/assets/img/tenge.png) no-repeat right 5px center #1E1D21;
        padding-right: 30px;
        color: white;
        background-size: 0.563vw;
    }

    .filters__spans{
        color: #EAC48B;
        font-weight: 500;
        font-size: 1.042vw;
        margin-right: 16px;
        margin-top: 1.667vw;
    }
    .filtcontm{
        margin-top: 1.042vw;
    }
    
    
    /* RARITY */
    
    .rarity{
        display: flex;
        flex-direction: column;
        margin-top: 20px;
    }
    .rarity__btn{
        color: white;
        padding: 0 0;
        display: flex;
        justify-content: space-between;
        font-weight: 600;
        font-size: 24px;
        
    }
    .rarity__btn:focus{
        box-shadow: 0 0 0 0.2rem rgb(0 123 255 / 0%);
    }
    .rarity .card{
        background-color: unset;
        padding: 0;
        border: 0;
    }

    .cheks__label{
        display: flex;
        align-items: center;
    }
    .customCheckbox {
        float: left;
        position: relative;  
        width: 24px;
        height: 24px;
        background-color: unset;
        border-radius: 2px;
        border: 1px solid white;
        border-radius: 5px;
        box-shadow: inset 0px 1px 0px rgba(0, 0, 0, 0.1);
        /*margin-right: 5px;*/
        margin-right: 0.26vw;
        overflow: hidden;
    }
    .customCheckbox.customCheckboxChecked {
    background: #753ef9;
    border: 1px solid white;
    }
    .customCheckbox input {
    opacity: 0;
    cursor: pointer;
    z-index: 5;
    width: 100%;
    height: 100%;
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    }
    .customCheckbox span {
    display: none;
    text-align: center;
    line-height: 20px;
    font-size: 90%;
    color: #222;
    }
    .customCheckbox.customCheckboxChecked span {
    display: block;
    }
    .cheks__span{
        font-weight: 500;
        font-size: 24px;
        margin-left: 15px;    
    }

    .filter__button{
        color: white;
        background-color: #F15A24;
        border-radius: 5px;
        margin-top: 3.646vw;
    }

/* CATALOG */
    .catalog{
        display: grid;
        grid-template-columns: repeat(5, 1fr);
        grid-column-gap: 25px;
        grid-row-gap: 25px;
        overflow-y: auto;
        scrollbar-width: thin;
    }

    .catalog::-webkit-scrollbar-track {
    background-color: #181820;
}
    .catalog::-webkit-scrollbar {
        width: 10px;
    }
    .catalog::-webkit-scrollbar-thumb {
    box-shadow: inset 0 0 20px #FF0027;
    }
    
    .item{
        cursor: pointer;
        display: flex;
        flex-direction: column;
        color: white;
        background: radial-gradient(82.39% 82.39% at 50% 50%, rgba(30, 29, 33, 0.4) 0%, rgba(60, 59, 63, 0.4) 100%);
        border-radius: 5px;
        height: fit-content;
        box-shadow: 2px 4px 10px #00000040;
        height: auto;
    }
    .item__top{
        /* position: relative; */
        display: flex;
        justify-content: flex-end;
        padding-right: 10px;
        padding-left: 10px;
        padding-top: 5px;
        
    }
    .item__rare{
        /* position: absolute; */
        /* top: 0; */
        background-color: #6D6D6D;
        padding: 4px 8px;
        border-radius: 5px;
        /* margin-right: 5px; */
        /* text-align: right; */
    }
    .item__name{
        /* position: absolute; */
        bottom: 0;
        margin-left: 5px;
        font-size: 1.250vw;
        font-weight: 500;
        color: white;
        padding-right: 10px;
        /* font-family: 'Roboto', sans-serif; */
        line-height: 1.5vw;
    }
    .item__img{
        width: 100%;
        height: 9vw;
    }
    .item__bottom{
        padding: 0 5px;
        display: flex;
        justify-content: space-between;
        font-size: 1.250vw;
        color: rgba(255, 255, 255, 0.3);
        font-weight: 400;
        margin-top: 5px;
    }
    .item__price{
        font-weight: 600;
        font-size: 1.250vw;
        padding: 0 10px;
        color: white;
        /* font-family: 'Roboto', sans-serif; */
        margin-top: 10px;
    }
    .item__bottomcont{
        flex-grow: 1;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }
    .item:hover{
        background: rgba(241, 90, 36, 0.4);
    }
    .catalog__topfilters{
        flex-direction: column;
    }
    
    @media screen and (max-width:480px){
        .catalog{
            grid-template-columns: repeat(2, 1fr);
            margin-top: 20px;
            grid-column-gap: 5px;
        }
        .reloadsort{
            width: 100%;
        }
        .dropdown__catalog{
            font-size: 4.25vw;
        }
        .prices__container{
            width: 100%;
        }
        .price__min{
            width: 35vw;
            font-size: 5.458vw;
            background-size: 15px;
        }
        .price__max{
            width: 35vw;
            font-size: 5.458vw;
            background-size: 15px;
        }
        .filtcontm{
            width: 100%;
        }
        .dropdown__filters{
            font-size: 6.25vw;
        }
        .filter__button{
            margin-top: 15px;
            margin-bottom: 15px;
        }
        .item__img{
            height: 38vw;
        }
        .catalog__topfilters{
            flex-wrap: wrap;
            flex-direction: column;
        }
        .catalog__search{
            width: 90vw;
            height: 15vw;
        }
        .shop{
            padding-top:70px;
        }
        .catalog__search::placeholder{
        color: white; 
        font-size: 24px !important;
        font-weight: 500;
        }
        .price__min::placeholder{
            font-size: 24px !important;
        }
        .price__max::placeholder{
            font-size: 24px !important;
        }
        .catalog__search{
            background-size: 20px;
        }
        .filters__spans{
            font-size: 5.042vw;
        }
        .pagination__prev{
            font-size: 3.25vw;    
        }
        .pagination__next{
            font-size: 3.25vw;    
        }
        .pagination__numbers{
            font-size: 3.25vw; 
        }
    }
    
</style>