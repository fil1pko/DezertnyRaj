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

        <div class="card">
            <p>
                Nakonfiguruj si vlastnú veľkosť balenia, príchuť alebo dokonca aj farbu! <br>
                Pokiaľ by si mal nejakú špeciálnu požiadavku alebo máš záujem objednať si <br>
                väčšie množstvo napíš nám správu nie je nič s čím si hravo neporadíme.  
            </p>
        </div>
    </section>

</template>

<style lang="scss">
    @import '../assets/style/colors.scss';
    @import '../assets/style/main.scss';

    #macronConfigurator{
        .card{
            background-color: lightgreen;
            font-family: $charis;
            p{
                font-size: 0.833vw;
            }
        }
    }
</style>