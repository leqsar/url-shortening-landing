<script setup>
  import { ref } from 'vue'
  import Header from './components/Header.vue'
  import TheMainBlock from './components/TheMainBlock.vue'
  import TheBanner from './components/TheBanner.vue'
  import Form from './components/Form.vue'
  import TheStatisticBlock from './components/TheStatisticBlock.vue'
  import UrlWrapper from './components/UrlWrapper.vue'

  const urlArray = ref([]);

  function shortenTheLink(url) {
    if(url !== '' && url ) {
      fetch(`https://api.shrtco.de/v2/shorten?url=${url.value}`)                   
        .then((res) => {
          return res.json()
        })
        .then((data) => {
          if(urlArray.value.length === 3) urlArray.value.shift()
          console.log(data);
          urlArray.value.push({
            origin: url.value,
            shortened: data.result.full_short_link
          })
        })
    }   
    }
</script>

<template>
  <Header />
  <TheMainBlock />
  <Form @set-short-urls="shortenTheLink"/>
  <UrlWrapper v-if="urlArray.length > 0" :urlArray="urlArray"/>
  <TheStatisticBlock />
  <TheBanner />
</template>

<style scoped>

</style>
