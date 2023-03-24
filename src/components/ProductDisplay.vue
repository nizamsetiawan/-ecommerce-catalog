<template>
    <div>
        <div  :class="{ 'm-bg': isMan(), 'w-bg': isWoman(), 'none': !isMan() && !isWoman() }">
            <div :class="{'m-container': isMan(), 'container': isWoman()}">
                <div :class="{'m-keterangan': isMan(), 'keterangan': isWoman()}">
                    <h1 :class="{'m-title': isMan(), 'title':isWoman()}">{{  product.title }}</h1>
                    
                    <span :class="{'m-category': isMan(), 'category': isWoman()}">{{  product.category }} </span>
                    <span :class="{'m-rating': isMan(), 'rating': isWoman()}">{{ product.rating.rate }}/5
                        <span v-if="isMan()">
                            <span v-if="Math.round(product.rating.rate)==0">
                                <img :src='m0' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                            </span>
                            <span v-if="Math.round(product.rating.rate)==1">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                            </span>
                            <span v-if="Math.round(product.rating.rate)==2">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                            </span>
                            <span v-if="Math.round(product.rating.rate)==3">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                            </span>
                            <span v-if="Math.round(product.rating.rate)==4">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m0' alt="" class="img-rate">
                            </span>
                            <span v-if="Math.round(product.rating.rate)==5">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m1' alt="" class="img-rate">
                                <img :src='m1' alt="" class="img-rate">
                            </span>
                        </span>
                        <span v-if="isWoman()">
                            <span v-if="Math.round(product.rating.rate)==0">
                                <img :src='w0' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                            </span>
                            <span v-if="Math.round(product.rating.rate)==1">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                            </span>
                            <span v-if="Math.round(product.rating.rate)==2">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                            </span>
                            <span v-if="Math.round(product.rating.rate)==3">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                            </span>
                            <span v-if="Math.round(product.rating.rate)==4">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w0' alt="" class="img-rate">
                            </span>
                            <span v-if="Math.round(product.rating.rate)==5">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w1' alt="" class="img-rate">
                                <img :src='w1' alt="" class="img-rate">
                            </span>
                        </span>
                    </span>
                    <hr>
                    <h1 :class="{'m-description': isMan(), 'description': isWoman()}">{{  product.description }}</h1>
                    <hr>
                    <h1 :class="{'m-price': isMan(), 'price': isWoman()}">${{  product.price }}</h1>
                    <div>
                        <button class="btn" :class="{'m-buy-btn': isMan(), 'buy-btn': isWoman()}">Buy Now</button>
                        <button class="btn" :class="{'m-next-btn': isMan(), 'next-btn': isWoman()}" @click="nextProduct()">Next</button>
                    </div> 
                </div>
                <div :class="{'m-gambar' : isMan(), 'gambar': isWoman()}">
                    <img :src="product.image" alt="Product Image" class="img">
                </div>
            
            </div>
        </div>
       <div v-if="!isMan() && !isWoman()">
            <div class="u-bg">
                <div class="u-container">
                    <div class="u-text">
                        <p class='u-p'>This product is unavailable to show</p>
                        <button class="u-next-btn btn" @click="nextProduct()">Next</button>
                    </div>
                </div>
            </div>
       </div>
    </div>
    
</template>

<script>
   export default {
        data(){
            return{
                product: [],
                index: 1,
                m0: require ('../assets/0-m.png'),
                m1: require ('../assets/1-m.png'),
                w0: require ('../assets/0-w.png'),
                w1: require ('../assets/1-w.png')
            }
        },

        methods: {
            load(){
                fetch('https://fakestoreapi.com/products/'+this.index)
                .then(res=>res.json())
                .then((json)=>{
                this.product=json
                })
                .catch((e)=>{
                alert(e)
                })
                console.clear();
            },
            nextProduct(){
                this.index++
                if (this.index>20) {
                    this.index=1
                }
                this.load()
            },
            isMan() {
                this.category= this.product.category
                if (this.category=='men\'s clothing'){
                    return true
                    
                } else {
                    return false  
                }
            },
            isWoman(){
                this.category= this.product.category
                if (this.category=='women\'s clothing'){
                    return true
                } else {
                    return false
                }
            }
            
        },

        mounted(){
            this.load();
            
        }
    }
</script>

<style>
.none {
    display: none;
}
hr {
    border: 1px solid rgba(0, 0, 0, 0.2);
    

    width: 542.5px;
    height: 0px;

    margin: 15px 0;


    clear: both;
}
.img-rate {
    height: 18px;
    width: 18px;
}
.m-bg {
    background-image: url('../assets/Component 2.png');
    background-repeat: no-repeat;
    background-size: 100% 548px;

    border-top: 1px solid #D6E6FF;
}
.m-container {
    width: 1034px;
    min-height: 580px;

    background: #FFFFFF;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    border-radius: 10px;

    margin: 0 auto;
    padding: 0;
    
    box-sizing: border-box;

    overflow: auto;
    margin-top: 126px;
    margin-bottom: 126px;
}
.m-title {
    width: 548px;
    min-height: 68px;


    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 28px;
    line-height: 34px;

    color: #002772;
}
.m-category {
    width: 149px;
    min-height: 22px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 22px;


    color: #3F3F3F;

        
    float: left;
    margin: 11px 0;
}
.m-rating {
    width: 50%;
    min-height: 22px;
    text-align: right;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 22px;


    color: #3F3F3F;

    float: right;

    margin: 11px 0;
}
.m-description {
    width: 517px;
    min-height: 163px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 20px;
    line-height: 24px;

    color: #1E1E1E;

    clear: both;
}
.m-price {
    width: 97px;
    min-height: 34px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 28px;
    line-height: 34px;

    margin-top: 15.5px;
    margin-bottom: 15.5px;
    color: #002772;
}

.img {
    box-sizing: border-box;

    width: 305.81px;
    height: 407px;

    border-radius: 10px;
    object-fit: contain;
}
.m-buy-btn {
    box-sizing: border-box;

    width: 259px;
    min-height: 42px;

    background: #002772;
    border-radius: 4px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 24px;

    color: #FFFFFF;

    margin-right: 19px;

}
.m-next-btn {
    box-sizing: border-box;

    width: 259px;
    min-height: 42px;

    background: #FFFFFF;
    border: 3px solid #720060;
    border-radius: 4px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 24px;

    color: #720060;

}
.m-keterangan {
    text-align: left;
    float:right;
    margin: 50px;
}
.m-gambar{
    float: left;
    margin: 50px 30px;
}
.w-bg {
    background-image: url('../assets/Component 1.png');
    background-repeat: no-repeat;
    background-size: 100% 548px;

    border-top: 1px solid #FDE2FF;
;
}
.container {
    width: 1034px;
    min-height: 580px;

    background: #FFFFFF;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    border-radius: 10px;

    margin: 0 auto;
    padding: 0;
    
    box-sizing: border-box;

    overflow: auto;
    margin-top: 126px;
    margin-bottom: 126px;
}
.title {
    width: 548px;
    min-height: 68px;


    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 28px;
    line-height: 34px;

    color: #720060;
}
.category {
    width: 149px;
    min-height: 22px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 22px;


    color: #3F3F3F;

        
    float: left;
    margin: 11px 0;
}
.rating {
    width: 50%;
    min-height: 22px;
    text-align: right;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 22px;


    color: #3F3F3F;

    float: right;

    margin: 11px 0;
}
.description {
    width: 517px;
    min-height: 163px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 20px;
    line-height: 24px;

    color: #1E1E1E;

    clear: both;
}
.price {
    width: 97px;
    min-height: 34px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 28px;
    line-height: 34px;

    margin-top: 15.5px;
    margin-bottom: 15.5px;

    color: #720060;
}

img {
    box-sizing: border-box;

    width: 305.81px;
    height: 407px;

    border-radius: 10px;
    object-fit: contain;
}
.buy-btn {
    box-sizing: border-box;

    width: 259px;
    min-height: 42px;

    background: #720060;
    border-radius: 4px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 24px;

    color: #FFFFFF;

    margin-right: 19px;

}
.next-btn {
    box-sizing: border-box;

    width: 259px;
    min-height: 42px;

    background: #FFFFFF;
    border: 3px solid #720060;
    border-radius: 4px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 24px;

    color: #720060;

}
.keterangan {
    text-align: left;
    float:right;
    margin: 50px;
}
.gambar{
    float: left;
    margin: 50px 30px;
}
.u-bg {
    background-image: url('../assets/Rectangle 5.jpg');
    background-repeat: no-repeat;
    background-size: 100% 548px;

    border-top: 1px solid #D8D7D7;
;
}
.u-container {
    top: 126px;
    background-image: url(../assets/sad-face.jpg);
    background-color: white;
    background-repeat: no-repeat;
    background-position-y: center;
    background-position-x: center;

    width: 1034px;
    min-height: 580px;

    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    border-radius: 10px;

    margin: 0 auto;
    padding:0;

    overflow: auto;

    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 126px;
    margin-bottom: 126px;
}
.u-next-btn {
    background: #FFFFFF;
    border: 3px solid #000000;
    border-radius: 4px;

    width: 465px;
    height: 42px;
}
.u-p {
    width: 332px;
    height: 24px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 20px;
    line-height: 24px;

    color: #000000;
    margin: 0 auto;
}
.btn:hover {
    opacity: 0.5;
}

@media screen and (max-width: 1000px) {
    .container, .m-container, .u-container {
        height: 100%;
        width: 100%;
        margin: auto;
    }
    .m-keterangan, .m-gambar, .m-rating, .m-category, .keterangan, .gambar, .rating, .category {
        float: none;
    }
    .rating, .m-rating, .category, .m-category, .title, .m-title {
        display: block;
        text-align: center;
        width: 100%;
    }
    .description, .m-description {
        width: 100%;
    }
    hr {
        width: 100%;
    }
    .u-container {
        background-size: contain;
    }
    .u-next-btn {
    width: 100%;
    }
    .gambar, .m-gambar {
        text-align: center;
    }
}
</style>