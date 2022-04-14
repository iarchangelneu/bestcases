<template>
    <div class="modal fade" id="ProductModal" tabindex="-1" aria-labelledby="ProductModal" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered">
            <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
                </button>
            </div>
            <div class="modal-body">
                <div class="row">
                    <div class="col-md-5 col-12">
                        <img :src="'/data/'+ product.item_model_id" alt="" class="productModal__img">    
                    </div>
                    <div class="col-md-7 col-12">
                        <div class="productModal__name">
                            {{product.full_type}} | {{product.name}}
                        </div> 
                        <div class="productModal__card">
                            
                            <ul class="productModal__table">
                                <li class="productModal__row">
                                    <span>
                                        Float
                                    </span>
                                    <span class="modal__value">
                                        {{product.gun_float}}
                                    </span>
                                </li>
                                <li class="productModal__row productModal__tableCenter">
                                    <span>
                                        Редкость
                                    </span>
                                    <span class="modal__value">
                                        {{product.rarity}}
                                    </span>
                                </li>
                                <li class="productModal__row">
                                    <span>
                                        Паттерн
                                    </span>
                                    <span class="modal__value">
                                        {{product.pattern}}
                                    </span>
                                </li>
                            </ul>

                            <div class="d-flex justify-content-between" style="margin-top:1.083vw;">
                                <span class="productModal__priceName">
                                    Стоимость:
                                </span>
                                <span class="productModal__price">
                                    {{ Math.floor(product.cost) }} ₸
                                </span>
                            </div>
                            <button class="productModal__btn mt-3" @click="AddToCart(product)">
                                    Добавить в корзину
                            </button>
                        </div>    
                    </div>
                </div>
            </div>
            <!-- <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-dismiss="modal">Закрыть</button>
                <button type="button" class="btn btn-primary">Сохранить изменения</button>
            </div> -->
            </div>
        </div>
    </div>
</template>

<script>
import {mapActions} from 'vuex'
export default {
    props: {
        product: Object,
    },
    methods: {
        ...mapActions([
            'AddToCart'
        ]),    
        closeProduct(){
            $('#ProductModal').modal('hide')
        }
    }
}
</script>

<style scoped>
.productModal__priceName{
    font-weight: 700;
    font-size: 1.250vw;
    /* font-family: 'Roboto', sans-serif; */
}
li::before {
    content: '';
    border-bottom: 1px dashed #ccc;
    flex-grow: 1;
    order: 2;
    margin: 0 5px;
}
.modal__value{
    order: 3;
}
.modal-body{
    margin-top: unset;
}
.modal-dialog{
    min-width: 51.510vw;    
}
#ProductModal{
    color: white;
}
#ProductModal .modal-header .close{
    padding: 1.5rem 2rem 1rem 1rem;   
    color: white; 
}
#ProductModal .modal-content{
    color: white;
    background-color: #1A1814;
}
.productModal__card{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    /* background-color: #252331; */
    padding: 1.042vw 1.563vw 2.083vw 0;
    border-radius: 10px;
}
.productModal__img{
    width: 70%;
    margin-left: 15%;
    margin-right: 15%;
}
.productModal__name{
    font-weight: 700;
    font-size: 1.354vw;
    text-align: left;
}
.productModal__table{
    margin-top: 1.823vw;  
    /* background-color: #3C3537; */
    border-radius: 10px;  
    padding-left: 0;
}
.productModal__row{
    padding: 1.042vw 0;
    font-weight: 500;
    font-size: 1.146vw;
    display: flex;
    justify-content: space-between;
}
.productModal__tableCenter{
    /* border-top: 1px solid #F6F6F6CC;
    border-bottom: 1px solid #F6F6F6CC; */
}
.productModal__btn{
    background: rgba(241, 90, 36, 0.4);
    border-color: #F15A24;
    border-radius: 5px;
    color: white;
    font-weight: 400;
    font-family: 'Roboto', sans-serif;
    font-size: 1.146vw;
}
.productModal__btnM{
    background: rgba(44, 109, 245, 0.2);
    border-color: #2C6DF5;
    border-radius: 5px;
    color: white;
    font-weight: 700;
    font-size: 1.146vw;
}
.productModal__price{
    font-weight: 400;
    font-size: 1.667vw;
    font-family: 'Roboto', sans-serif;
}
@media screen and (min-width:481px){
    .productModal__btnM{
        display: none;
    }
}
@media screen and (max-width:480px){
    .productModal__name{
        font-size: 14px;
    }
    .productModal__table{
        border-radius: 5px;
    }
    .productModal__row{
        font-size: 12px;
    }
    .productModal__btnM{
        font-size: 8px;
    }
    .productModal__price{
        font-size: 14px;
    }
    .productModal__btn{
        display: none;
    }
    .productModal__card{
        padding: 3.042vw 1.563vw 4.083vw 1.563vw;
    }
}
</style>