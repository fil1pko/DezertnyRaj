<script>

</script>

<template>
    <section id="home">
        <div class="choice-wraper first">
            <div class="overlay green">
                <article>
                    <h2>Tortová Slasť</h2>
                    <div class="line"></div>
                    <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Animi facilis quia soluta laudantium numquam, libero accusamus illo. Eligendi iusto animi nostrum molestiae ea at eos minima quis sit, consequuntur vel?</p>
                </article>
            </div>

            <img src="../assets/pictures/cake.png" alt="Torta">
        </div>

        <div class="choice-wraper second">
            <div class="overlay red">
                <article>
                    <h2>Makrónkový Pôvab</h2>
                    <div class="line2"></div>
                    <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Animi facilis quia soluta laudantium numquam, libero accusamus illo. Eligendi iusto animi nostrum molestiae ea at eos minima quis sit, consequuntur vel?</p>
                </article>
            </div>

            <img src="../assets/pictures/macron.png" alt="Makrónka">
        </div>
    </section>
</template>

<style lang="scss">
    @import '../assets/style/colors.scss';
    @import '../assets/style/main.scss';

    #home{
        max-width: clamp(19rem,97.979vw,232.688rem);
        margin: 0 auto;    
        display: flex;
        justify-content: space-between;
        height: 750px;
        margin-top: 40px;
        .choice-wraper{
            width: 930px;
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            .overlay{
                position: absolute;
                font-family: $charis;
                width: 100%;
                height: 100%;
                opacity: 0;
                display: flex;
                justify-content: center;
                align-items: center;
                transition: 0.8s;
                &:hover{
                    opacity: 1;
                }
                article{
                    display: flex;
                    justify-content: center;
                    align-items: center;

                    flex-direction: column;
                    max-width: 60%;
                    gap: 6px;
                    h2{
                        font-weight: bold;
                        font-size: 30px;
                    }
                    p{
                        text-align: center;
                    }
                    .line{
                        height: 1px;
                        width: 81px;
                        background-color: $black;
                    }
                    .line2{
                        height: 1px;
                        width: 81px;
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
</style>