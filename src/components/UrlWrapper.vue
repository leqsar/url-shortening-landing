<script setup>
    import { ref, onBeforeUpdate } from 'vue'
    import AOS from 'aos'
    import 'aos/dist/aos.css'
    import { onMounted } from 'vue'

    const props = defineProps(['urlArray'])
    const shortenedLink = ref()
    const divs = ref([])

    onBeforeUpdate(() => {
        divs.value = []
    })

    onMounted(() => {
      AOS.init()
    })

    function copyUrl (index) {
        navigator.clipboard.writeText(divs.value[index].textContent)
    }
</script>

<template>
    <ul>
        <li class="links-wrapper" data-aos="fade-left" data-aos-duration="1000" v-for="(link, i) in urlArray" >
            <p class="original">{{link.origin}}</p>
            <p 
                class="shortened" 
                :ref="el => { if (el) divs[i] = el }"
            >
                {{link.shortened}}
            </p>
            <button @click="copyUrl(i)">Copy</button>
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

        .original
            justify-self: start
            font-weight: 700
            overflow: hidden
        .shortened
            justify-self: end
            color: $cyan
            font-weight: 700

        button 
            justify-self: end
            margin-left: 2%
            width: 100px
            border-radius: 10px

</style>
