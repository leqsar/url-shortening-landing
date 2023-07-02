<script setup>

</script>

<template>
    <form action="" class="form">
        <input type="text" class="input">
        <button>Shorten It!</button>
    </form>
</template>

<style scoped lang="sass">

    @import '../input.sass'

    .form
        display: flex
        align-items: center
        gap: 25px
        width: 77%
        height: 170px
        margin: 0 auto
        margin-top: 70px
        padding: 0 6%
        background-color: $darkViolet
        background-image: url('../assets/images/bg-shorten-desktop.svg')
        border-radius: 10px
        box-sizing: border-box

        .input
            width: 80%
            height: 65px
            border-radius: 15px

        button
            width: 20%
            height: 65px


</style>
