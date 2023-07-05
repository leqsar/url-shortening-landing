<script setup></script>

<template>
  <div class="main-wrapper">
    <img src="../assets/images/illustration-working.svg" alt="Illustration">
    <h1 class="main-heading">More than just shorter links</h1>
    <p class="main-info">
      Build your brand’s recognition and get detailed insights on how your links
      are performing.
    </p>
    <button class="main-button">Get Started</button>
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

        @media screen and (max-width: 520px)
          padding-top: 20px

        .main-heading
            width: 40%
            font:
                size: 65px
                weight: 700
            line-height: 65px
            color: $veryDarkViolet

            @media screen and (max-width: 520px)
              width: 100%
              text-align: center
        
        .main-info
            width: 37%
            margin-top: 30px
            color: $grayishViolet

            @media screen and (max-width: 520px)
              width: 100%
              text-align: center

        .main-button
            margin-top: 40px
            width: 195px
            height: 55px
            border-radius: 22px

            @media screen and (max-width: 520px)
              width: 100%

        img
            position: absolute
            top: 0
            right: 0
            aspect-ratio: 733/482
            z-index: -1

            @media screen and (max-width: 1024px)
              top: 100px
              width: 60%

            @media screen and (max-width: 520px)
              position: relative
              top: 0
              width: 100%

</style>
