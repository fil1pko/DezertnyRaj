<script>
    export default {
        methods: {
            handleClick() {
            this.$emit('buttonClick');
            },
        },
    };
</script>

<template>
    <section id="macronConfigurator">
        <div @click="handleClick">
            <img src="../assets/pictures/goBack.svg" alt="Ísť späť">
        </div>

        <div class="choice-img">
            <img src="../assets/pictures/macron.png" alt="Tvoja volba">
        </div>

        <article>
            <!-- intro -->
            <p>
                Nakonfiguruj si vlastnú veľkosť balenia, príchuť alebo dokonca aj farbu! Pokiaľ by si mal nejakú špeciálnu požiadavku alebo máš záujem objednať si<br>väčšie množstvo napíš nám správu nie je nič s čím si hravo neporadíme.  
            </p>

            <!-- volba velkosti -->
            <p>
                Vyber si veľkosť.
            </p>
            <div class="button-wraper">
                <div class="button small"> L </div>
                <div class="button small"> M </div>
                <div class="button small"> S </div>
                <div class="button small teaser"> Teaser </div>
                <p style="padding-top: 0;">Počet kusov v balení: <b>30</b></p>
            </div>

            <!-- volba prichute -->
            <p>
                Vyber si nejakú z našich vychytených príchutí.
            </p>
            <div class="button-wraper">
                <div class="button big">
                    <h6 id="red">ČERVENÁ</h6>
                    <small>Lesná zmes</small>
                </div>
                <div class="button big">
                    <h6 id="brown">HNEDÁ</h6>
                    <small>Káva</small>
                </div>
                <div class="button big">
                    <h6 id="white">BIELA</h6>
                    <small>Karamel</small>
                </div>
                <div class="button big">
                    <h6 id="green">ZELENÁ</h6>
                    <small>Pistácie</small>
                </div>
            </div>


            <!-- email set -->
            <p>
                Zadaj mail, v ktorom sa dohodneme na detailoch a dodaní, zároveň žiadame o vyriešenie jednoduchého príkladu aby sme si overrili, že nie si robot. 
            </p>
            <div class="button-wraper form-wraper">
                <form>
                    <div class="longer">
                        <input class="custom-input" type="mail" placeholder="examplemail@gmail.com">
                    </div>
                    <div class="shorter">
                        <input class="custom-input2" type="text" placeholder="4+5">
                    </div>

                    <button type="submit">Objednať</button>
                </form>
            </div>
            <p>
                Chceš to nakombinovať úple podľa seba? Tu nám napíš svoju predstavu.    
            </p>
        </article>
    </section>

</template>

<style lang="scss">
    @import '../assets/style/colors.scss';
    @import '../assets/style/main.scss';

    #macronConfigurator{
        width: 100%;
        @include flex;
        gap: 50px;
        margin: 0 auto;    
        height: 39.063vw; //235.125rem
        margin-bottom: 2.083vw; 
        article{
            font-family: $charis;
            text-align: justify;
            max-width: 28%;
            align-self: center;
            p{
                font-size: 0.833vw;
                padding-top: 30px;
            }
            .button-wraper{
                display: flex;
                justify-content: space-between;
                align-items: center;
                .button{
                    @include flex;
                    background-image: url('../assets/pictures/orbBorder.svg');
                    background-repeat: no-repeat;
                    background-size: contain;
                    cursor: pointer;
                    #red{
                        color: $redText;
                    }
                    #brown{
                        color: $brown;
                    }
                    #white{
                        color: $black;
                    }
                    #green{
                        color: $greenText;
                    }
                }
                h6{
                    font-weight: bold;
                    font-size: 0.933vw;
                }
                .small{
                    width: 70px;
                    height: 49px;
                }

                .big{
                    width: 130px;
                    height: 91px;
                    flex-direction: column;
                }
            }
            .form-wraper{
                form{
                    display: flex;
                    align-items: center;
                    .longer{
                        background-image: url('../assets/pictures/orbBorderLong.svg');
                        background-repeat: no-repeat;
                        background-size: cover; 
                        @include flex;

                        width: 280px;
                        height: 48px;
                        .custom-input{
                            all: unset;
                        }
                    }
                    .shorter{
                        background-image: url('../assets/pictures/orbBorder.svg');
                        background-repeat: no-repeat;
                        background-size: cover; 
                        @include flex;

                        width: 73px;
                        height: 53px;
                        .custom-input2{
                            font-size: 0.733vw !important;
                            all: unset;
                            width: 40%;
                        }
                    }

                    button{
                        all: unset;
                        background-image: url('../assets/pictures/orbBorder.svg');
                        background-repeat: no-repeat;
                        background-size: cover; 
                        @include flex;
                        cursor: pointer;
                        font-size: 12px;
                        font-weight: bold;
                        width: 73px;
                        height: 53px;
                    }
                }
            }
        }
        .choice-img{
            display: flex;
            align-items: center;
        }
    }
</style>