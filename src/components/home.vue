<script>
    export default {
        methods: {
            handleClick() {
                this.$emit('buttonClick')
            },
            handleClick2(){
               this.$emit('buttonClick2') 
            }
        },
    };
</script>

<template>
    <section id="home">
        <div class="choice-wraper first">
            <div @click="handleClick2" class="overlay green">
                <article>
                    <h2>Tortová Slasť</h2>
                    <div class="line"></div>
                    <p>Na dobré si treba počkať!</p>
                </article>
            </div>
            <div class="content-wraper">
                <div class="orb-wraper">
                    <img src="../assets/pictures/orbLeftUp.svg" alt="Orb left">
                    <img src="../assets/pictures/orbRightUp.svg" alt="Orb right">
                </div>

                <div class="image-wraper">
                    <img src="../assets/pictures/cake.png" alt="Torta">
                </div>

                <div class="orb-wraper">
                    <img src="../assets/pictures/orbLeftDown.svg" alt="Orb left">
                    <img src="../assets/pictures/orbRightDown.svg" alt="Orb right">
                </div>
            </div>
        </div>


        <!-- macrons -->
        <div class="choice-wraper second">
            <div @click="handleClick" class="overlay red">
                <article>
                    <h2>Makrónkový Pôvab</h2>
                    <div class="line2"></div>
                    <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Animi facilis quia soluta laudantium numquam, libero accusamus illo. Eligendi iusto animi nostrum molestiae ea at eos minima quis sit, consequuntur vel?</p>
                </article>
            </div>
            <div class="content-wraper">
                <div class="orb-wraper">
                    <img src="../assets/pictures/orbLeftUp.svg" alt="Orb left">
                    <img src="../assets/pictures/orbRightUp.svg" alt="Orb right">
                </div>

                <div class="image-wraper">
                    <img src="../assets/pictures/macron.png" alt="Makrónka">
                </div>

                <div class="orb-wraper">
                    <img src="../assets/pictures/orbLeftDown.svg" alt="Orb left">
                    <img src="../assets/pictures/orbRightDown.svg" alt="Orb right">
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss">
    @import '../assets/style/colors.scss';
    @import '../assets/style/main.scss';

    #home{
        max-width: clamp(19rem,97.979vw,238.688rem);
        margin: 0 auto;    
        display: flex;
        justify-content: space-between;
        height: 39.063vw; //235.125rem
        margin-top: 2.083vw; //5rem
        .choice-wraper{
            width: 48.438vw; //116.25rem
            max-width: 116.25rem;
            position: relative;

            .content-wraper{
                height: 100%;
                display: flex;
                flex-direction: column;
                justify-content: space-between;
                padding: 0.521vw; //1.25rem
                .orb-wraper{
                    width: 100%;
                    display: flex;
                    justify-content: space-between;
                    img{
                        opacity: 0.8;
                        width: 5.729vw;  //13.75rem
                    }
                }
                .image-wraper{
                    width: 100%;
                    @include flex;
                }
            }


            .overlay{
                position: absolute;
                font-family: $charis;
                width: 100%;
                height: 100%;
                opacity: 0;
                @include flex;
                transition: 0.8s;
                cursor: pointer;
                &:hover{
                    opacity: 1;
                }
                article{
                    @include flex;
                    flex-direction: column;
                    max-width: 60%;
                    gap: 0.313vw; //0.75rem
                    h2{
                        font-weight: bold;
                        font-size: 1.563vw; //3.75rem
                    }
                    p{
                        text-align: center;
                        font-size: 0.833vw; //2rem
                    }
                    .line{
                        height: 0.052vw; //0.125rem 
                        width: 4.219vw; //10.125rem
                        background-color: $black;
                    }
                    .line2{
                        height: 0.052vw;
                        width: 4.219vw;
                        background-color: $white;
                    }
                }
            }
            .red{
                background: $redBg2;
                color: $white;
            }
            .green{
                background: $green2;
                color: $black;
            }
        }
        .first{
            background-color: $green;
        }
        .second{
            background-color: $redBg;
        }
    }
    @media only screen and (max-width: 1024px){
        #home{
            flex-direction: column;
        }
    }
</style>