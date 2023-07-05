<script setup>
    import { ref, onBeforeUpdate } from 'vue'
    import AOS from 'aos'
    import 'aos/dist/aos.css'
    import { onMounted } from 'vue'

    const props = defineProps(['urlArray'])
    const shortenedLink = ref()
    const links = ref([])

    onBeforeUpdate(() => {
        links.value = []
    })

    onMounted(() => {
      AOS.init()
    })

    function copyUrl (event, index) {
        const button = event.currentTarget
        button.textContent = 'Copied!'
        button.style.backgroundColor = 'hsl(257, 27%, 26%)'
        setTimeout(() => {
            button.textContent = 'Copy'
            button.style.backgroundColor = 'hsl(180, 66%, 49%)'
        }, 600)
        navigator.clipboard.writeText(links.value[index].textContent)
    }
</script>

<template>
    <ul>
        <li class="links-wrapper" data-aos="fade-left" data-aos-duration="1000" v-for="(link, i) in urlArray" >
            <p class="original">{{link.origin}}</p>
            <p 
                class="shortened" 
                :ref="el => { if (el) links[i] = el }"
            >
                {{link.shortened}}
            </p>
            <button @click="copyUrl($event, i)">Copy</button>
        </li>
    </ul>
</template>

<style scoped lang="sass">

    @import '../input.sass'

    .links-wrapper
        display: grid
        align-items: center
        grid-template-columns: 63% 23% 10%
        gap: 2%
        width: 77%
        height: 75px
        margin: 0 auto
        margin-top: 30px
        padding: 0 2%
        box-sizing: border-box
        border-radius: 10px
        background-color: white

        @media screen and (max-width: 520px)
            height: 156px
            grid-template-rows: repeat(3, 1fr)
            grid-template-columns: 100%

        .original
            position: relative
            justify-self: start
            font-weight: 700
            overflow: hidden

            @media screen and (max-width: 520px)
                justify-self: center

                &::after
                    content: ''
                    position: absolute
                    top: 100%
                    left: 0
                    width: 100%
                    border: 2px solid black

        .shortened
            justify-self: end
            color: $cyan
            font-weight: 700

            @media screen and (max-width: 520px)
                justify-self: center

        button 
            justify-self: end
            margin-left: 2%
            width: 100px
            border-radius: 10px
            transition: all 0.6s

            @media screen and (max-width: 520px)
                width: 80%
                justify-self: center

</style>
