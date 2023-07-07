<script setup>
import {ref} from 'vue'

const menuVisible = ref(false)

function switchMenuVisibility() {
  menuVisible.value = menuVisible.value ? false : true
}

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
    <img 
      class="burger-icon"
      @click="switchMenuVisibility"
      src="../assets/images/burger.svg" 
      alt=""
    >
    <div v-show="menuVisible">
      <nav class="navigation-wrapper__mob">
        <ul class="navigation__mob">
          <li>Features</li>
          <li>Pricing</li>
          <li>Resources</li>
        </ul>
        <button class="login-button">Login</button>
        <button class="signup-button">Sign up</button>
      </nav>
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
    box-sizing: border-box

    @media screen and (max-width: 500px)
      position: relative
      padding-right: 2%

    .navigation-wrapper
      display: flex
      max-width: 275px
      width: 20%
      margin-left: 3%

      @media screen and (max-width: 1250px)
        width: 30%

      @media screen and (max-width: 500px)
        display: none


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

      @media screen and (max-width: 500px)
        display: none
      .login-button
        color: $grayishViolet
        font-weight: 700
        border: none
        background: none
      
      .signup-button
        width: 105px
        margin-left: 40px


    .burger-icon
      position: absolute
      right: 2%
      display: none
      width: 20px
      height: 20px

      &:hover
        cursor: pointer
      
      @media screen and (max-width: 500px)
        display: block

    .navigation-wrapper__mob
      display: none
      position: absolute
      width: 94%
      height: 390px
      left: 3%
      top: 130px
      border-radius: 10px
      background-color: $darkViolet
      color: $white
      z-index: 10

      .navigation__mob
        position: relative
        display: flex
        width: 100%
        height: 200px
        margin-top: 20px
        flex-direction: column
        align-items: center
        justify-content: space-evenly

        &::after
          position: absolute
          content: ''
          top: 100%
          width: 70%
          border: 1px solid $grayishViolet

      .login-button
        width: 70%
        margin: 0 auto
        margin-top: 20px
        background-color: inherit

      .signup-button
        width: 70%
        margin: 0 auto
        margin-top: 20px
      
      @media screen and (max-width: 500px)
        display: flex
        flex-direction: column


</style>
