<script setup>

</script>

<template>
    <div class="banner-wrapper">
        <h2 class="banner-header">Boost your links today</h2>
        <button class="banner-button">Get Started</button>
    </div>
</template>

<style scoped lang="sass">

    @import '../input.sass'

    .banner-wrapper
        display: flex
        flex-direction: column
        justify-content: center
        align-items: center
        width: 100%
        height: 250px
        margin-top: 129px
        background-color: $darkViolet
        background-image: url('../assets/images/bg-boost-desktop.svg')

        .banner-header 
            font: 
                size: 30px
                weight: 700
            color: $white

        .banner-button 
            margin-top: 40px
            width: 195px
            height: 55px
            border-radius: 27px


</style>
