<script setup></script>

<template>
  <div class="main-wrapper">
    <h1 class="main-heading">More than just shorter links</h1>
    <p class="main-info">
      Build your brand’s recognition and get detailed insights on how your links
      are performing.
    </p>
    <button class="main-button">Get Started</button>
    <img src="../assets/images/illustration-working.svg" alt="Illustration">
  </div>
</template>

<style scoped lang="sass">

    @import '../input.sass'

    .main-wrapper
        position: relative
        width: 100%
        min-height: 491px
        margin-top: 40px
        padding-left: 7%
        padding-top: 80px
        box-sizing: border-box

        .main-heading
            width: 40%
            font:
                size: 65px
                weight: 700
            line-height: 65px
            color: $veryDarkViolet
        
        .main-info
            width: 37%
            margin-top: 30px
            color: $grayishViolet

        .main-button
            margin-top: 40px
            width: 195px
            height: 55px
            border-radius: 22px

        img
            position: absolute
            top: 0
            right: 0
            z-index: -1


</style>
