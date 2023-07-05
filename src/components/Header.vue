<script setup>
</script>

<template>
  <header class="header-wrapper">
    <img src="../assets/images/logo.svg" alt="Company logo">
    <nav class="navigation-wrapper">
      <ul class="navigation">
        <li>Features</li>
        <li>Pricing</li>
        <li>Resources</li>
      </ul>
    </nav>
    <div class="button-wrapper">
      <button class="login-button">Login</button>
      <button class="signup-button">Sign up</button>
    </div>
  </header>
</template>

<style scoped lang="sass">

  @import '../input.sass'

  .header-wrapper
    display: flex
    align-items: center
    width: 100%
    height: 130px
    padding-left: 7%

    .navigation-wrapper
      max-width: 275px
      width: 20%
      margin-left: 3%

      @media screen and (max-width: 1250px)
        width: 30%


      .navigation
        display: flex
        justify-content: space-between
        width: 100%
        font-weight: 500
        color: $grayishViolet
        letter-spacing: 0.5px

        li

          &:hover
            cursor: pointer
            color: $veryDarkViolet
            font-weight: 700

    .button-wrapper
      display: flex
      width: max-content
      margin-left: 34%

      @media screen and (max-width: 1024px)
        margin-left: 24%
      .login-button
        color: $grayishViolet
        font-weight: 700
        border: none
        background: none
      
      .signup-button
        width: 105px
        margin-left: 40px


</style>
