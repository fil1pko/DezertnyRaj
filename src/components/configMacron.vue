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
        <div @click="handleClick" style="width: 30px; height: 30px; background-color: red; cursor: pointer;">
            <p>macron config</p>
        </div>

        <div class="choice-img" style="background-color: red;">
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
                <p>Počet kusov v balení: <b>30</b></p>
            </div>

            <!-- volba prichute -->
            <p>
                Vyber si nejakú z našich vychytených príchutí.
            </p>
            <div class="button-wraper">
                <div class="button big">
                    <h6>ČERVENÁ</h6>
                    <small>Lesná zmes</small>
                </div>
                <div class="button big">
                    <h6>HNEDÁ</h6>
                    <small>Káva</small>
                </div>
                <div class="button big">
                    <h6>BIELA</h6>
                    <small>Karamel</small>
                </div>
                <div class="button big">
                    <h6>ZELENÁ</h6>
                    <small>Pistácie</small>
                </div>
            </div>


            <!-- email set -->
            <p>
                Zadaj mail, v ktorom sa dohodneme na detailoch a dodaní, zároveň žiadame o vyriešenie jednoduchého príkladu aby sme si overrili, že nie si robot. 
            </p>
            <div class="button-wraper form-wraper">
                <form>
                    <input type="mail" class="longer">
                    <input type="text" class="shorter">
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
        justify-content: center;
        margin: 0 auto;    
        display: flex;
        height: 39.063vw; //235.125rem
        margin-top: 2.083vw; //5rem
        article{
            background-color: lightgreen;
            font-family: $charis;
            p{
                font-size: 0.833vw;
            }
            .button-wraper{
                display: flex;
                align-items: center;
                .button{
                    @include flex;
                    background-image: url('../assets/pictures/orbBorder.svg');
                    background-repeat: no-repeat;
                    background-size: contain;
                    cursor: pointer;
                }
                h6{
                    font-size: 0.833vw;
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
                flex-direction: column;
                form{
                    .longer{
                        all: unset;
                        width: 280px;
                        height: 44px;
                        background-image: url('../assets/pictures/orbBorderLong.svg');
                        background-repeat: no-repeat;
                        background-size: cover;
                    }
                    .shorter{
                        all: unset;
                        height: 44px;
                        background-image: url('../assets/pictures/orbBorderLong2.svg');
                        background-repeat: no-repeat;
                        background-size: cover;
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