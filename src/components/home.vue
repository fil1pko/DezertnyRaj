<script>

</script>

<template>
    <section id="home">
        <a class="choice-wraper first" href="">
            <div class="overlay green">
                <article>
                    <h2>Tortová Slasť</h2>
                    <div class="line"></div>
                    <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Animi facilis quia soluta laudantium numquam, libero accusamus illo. Eligendi iusto animi nostrum molestiae ea at eos minima quis sit, consequuntur vel?</p>
                </article>
            </div>

            <img src="../assets/pictures/cake.png" alt="Torta">
        </a>

        <a class="choice-wraper second" href="">
            <div class="overlay red">
                <article>
                    <h2>Makrónkový Pôvab</h2>
                    <div class="line"></div>
                    <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Animi facilis quia soluta laudantium numquam, libero accusamus illo. Eligendi iusto animi nostrum molestiae ea at eos minima quis sit, consequuntur vel?</p>
                </article>
            </div>

            <img src="../assets/pictures/macron.png" alt="Makrónka">
        </a>
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
                width: 100%;
                height: 100%;
                opacity: 0;
                color: $black;
                display: flex;
                justify-content: center;
                align-items: center;
                transition: 0.8s;
                h2{
                    font-weight: bold;
                    font-size: 30px;
                }
                &:hover{
                    opacity: 1;
                }
            }
            .red{
                background: $redBg;
            }
            .green{
                background: $green;
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