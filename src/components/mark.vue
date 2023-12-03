<script>
</script>

<template>
    <div class="mark">
        <small>© 2023 made by <a href="https://github.com/fil1pko">RU3Y</a> All Rights Reserved</small>
    </div>
</template>

<style lang="scss">
    @import '../assets/style/colors.scss';
    @import '../assets/style/main.scss';

    .mark{
        font-family: $charis;
        width: 100%;
        @include flex;
        padding-top: 1.042vw;
        small{
            font-size: 0.677vw;
            a{
                font-weight: bold;
                text-decoration: none;
                color: $black;
            }
        }
    }
</style>