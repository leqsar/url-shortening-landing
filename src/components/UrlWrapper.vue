<script setup>
    const props = defineProps(['urlArray'])
</script>

<template>
    <ul>
        <li v-for="link in urlArray" class="links-wrapper">
            <p class="original">{{link.origin}}</p>
            <p class="shortened">{{link.shortened}}</p>
            <button>Copy</button>
        </li>
    </ul>
</template>

<style scoped lang="sass">

    @import '../input.sass'

    .links-wrapper
        display: flex
        align-items: center
        width: 77%
        height: 75px
        margin: 0 auto
        margin-top: 30px
        padding: 0 2%
        box-sizing: border-box
        border-radius: 10px
        background-color: white

        .original
            justify-self: flex-start
            font-weight: 700
            overflow: hidden
        .shortened
            justify-self: flex-end
            color: $cyan
            font-weight: 700

        button 
            justify-self: flex-end
            margin-left: 2%
            width: 100px
            border-radius: 10px

</style>
