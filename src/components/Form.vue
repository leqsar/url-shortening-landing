<script setup>
    import { ref } from 'vue'

    const url = ref('');

    const props = defineProps(['error'])

    const emit = defineEmits(['setShortUrls']);

    function callEmit() {
        emit('setShortUrls', url) 
    }

</script>

<template>
    <form action="submit" @submit.prevent="callEmit" class="form">
        <input 
            type="text"
            placeholder="Shorten a link here ..."
            class="input" 
            :class="{'input-error': error}" 
            v-model="url"
        >
        <p class="error" v-show="error">Please add a link</p>
        <button>Shorten It!</button>
    </form>
</template>

<style scoped lang="sass">

    @import '../input.sass'

    .form
        position: relative
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
            padding-left: 20px
            font-size: 20px
            border-radius: 15px

            &:focus
                border: none
                outline: none

        .input-error
            border: 4px solid $red

        button
            width: 20%
            height: 65px

    .error
        position: absolute
        top: 125px
        left: 8%
        color: $red


</style>
