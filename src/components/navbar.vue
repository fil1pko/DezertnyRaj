<script>
export default {
    
}
</script>

<template>
    <nav>
        <img class="logo" src="../assets/pictures/logo.svg" alt="Logo">

        <h1>Dezertný raj <br> navštívi váš kraj</h1>

        <a href=""><img class="instagram" src="../assets/pictures/instagram.svg" alt="Instagram logo"></a>
    </nav>
</template>

<style lang="scss">
    @import '../assets/style/colors.scss';
    @import '../assets/style/main.scss';

    nav{
        position: relative;
        top: clamp(0.6rem,0.729vw,2.2rem); 
        @include flex;
        -webkit-box-pack: justify;
            -ms-flex-pack: justify;
                justify-content: space-between;
        max-width: clamp(19rem,96.979vw,232.688rem);
        margin: 0 auto;
        h1{
            text-align: center;
            color: $black;
            font-family: $heading;
            font-size: clamp(1.6rem,2.604vw,6rem);
            line-height: clamp(1.5rem,2.5vw,5.85rem);
        }
        .logo{
            width: clamp(3rem,4.271vw,9.938rem); 
        }
        .instagram{
            width: clamp(2rem,2.708vw,6.438rem); 
        }
    }
</style>