<script setup>
  import { ref, onMounted } from 'vue'
  import Header from './components/Header.vue'
  import TheMainBlock from './components/TheMainBlock.vue'
  import TheBanner from './components/TheBanner.vue'
  import Form from './components/Form.vue'
  import TheStatisticBlock from './components/TheStatisticBlock.vue'
  import UrlWrapper from './components/UrlWrapper.vue'

  const urlArray = ref([])
  const error = ref(false)

  onMounted(() => {
    const storageArray = JSON.parse(sessionStorage.getItem('linkArray'))
    if(storageArray.length > 0) {
      urlArray.value = storageArray
    }
  })

  function shortenTheLink(url) {
    const pureUrl = url.value
    if(pureUrl === '' || !pureUrl) error.value = true
    if(pureUrl !== '' && pureUrl ) {
      error.value = false
      fetch(`https://api.shrtco.de/v2/shorten?url=${pureUrl}`)                   
        .then((res) => {
          return res.json()
        })
        .then((data) => {
          if(urlArray.value.length === 3) urlArray.value.shift()
          urlArray.value.push({
            origin: pureUrl,
            shortened: data.result.full_short_link
          })
          sessionStorage.setItem('linkArray', JSON.stringify(urlArray.value))
        })
    }   
    }
</script>

<template>
  <Header />
  <TheMainBlock />
  <Form @set-short-urls="shortenTheLink" :error="error"/>
  <UrlWrapper v-if="urlArray.length > 0" :urlArray="urlArray"/>
  <TheStatisticBlock />
  <TheBanner />
</template>

<style scoped>

</style>
