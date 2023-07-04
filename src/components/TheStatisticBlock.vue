<script setup>
    import AOS from 'aos'
    import 'aos/dist/aos.css'
    import { onMounted } from 'vue'

    onMounted(() => {
      AOS.init()
    })
</script>

<template>
  <div class="statistic-wrapper">
    <h2 class="heading">Advanced Statistic</h2>
    <p class="additional-info">
      Track how your links are performing across the web with our advanced
      statistics dashboard.
    </p>
    <ul class="cards-wrapper">
      <li class="card" data-aos="fade-up" data-aos-duration="1000">
        <div class="icon-wrapper">
            <img src="../assets/images/icon-brand-recognition.svg" alt="Graph icon">
        </div>
        <h3>Brand Recognition</h3>
        <p>
          Boost your brand recognition with each click. Generic links don’t mean
          a thing. Branded links help instil confidence in your content.
        </p>
      </li>
      <li class="card" data-aos="fade-up" data-aos-duration="1000">
        <div class="icon-wrapper">
            <img src="../assets/images/icon-detailed-records.svg" alt="Compass icon">
        </div>
        <h3>Detailed Records</h3>
        <p>
          Gain insights into who is clicking your links. Knowing when and where
          people engage with your content helps inform better decisions.
        </p>
      </li>
      <li class="card" data-aos="fade-up" data-aos-duration="1000">
        <div class="icon-wrapper">
            <img src="../assets/images/icon-fully-customizable.svg" alt="Brushes icon">
        </div>
        <h3>Fully Customizable</h3>
        <p>
          Improve brand awareness and content discoverability through
          customizable links, supercharging audience engagement.
        </p>
      </li>
    </ul>
  </div>
</template>

<style scoped lang="sass">

    @import '../input.sass'

    .statistic-wrapper
        display: flex
        flex-direction: column
        align-items: center
        width: 100%
        margin-top: 140px
        padding: 0 7%
        box-sizing: border-box

        .heading
            font: 
                size: 30px
                weight: 700

        .additional-info
            width: 36%
            margin-top: 40px
            color: $gray
            line-height: 20px

        .cards-wrapper
            position: relative
            display: grid
            grid-template-columns: repeat(3, 1fr)
            align-items: center
            margin-top: 80px
            width: 100%
            height: 400px
            gap: 30px

            .card
                position: relative
                height: 270px
                padding: 90px 5% 0px 5%
                border-radius: 10px
                box-sizing: border-box
                box-shadow: 1px 0px  2px  2px $gray
                z-index: 10

                

                &:first-of-type
                    align-self: start
                    &::after
                        content: ''
                        position: absolute
                        top: 50%
                        right: -30px
                        width: 25px
                        border: solid 3px $cyan

                &:last-of-type
                    align-self: end
                    &::after
                        content: ''
                        position: absolute
                        top: 50%
                        left: -30px
                        width: 25px
                        border: solid 3px $cyan
                    
                h3
                    font:
                        size: 20px
                        weight: 700

                p
                    margin-top: 20px
                    font-size: 16px
                    color: $gray

                .icon-wrapper
                    position: absolute
                    display: flex
                    justify-content: center
                    align-items: center
                    top: -40px
                    left: 5%
                    width: 80px
                    height: 80px
                    border-radius: 40px
                    background-color: $darkViolet

</style>
