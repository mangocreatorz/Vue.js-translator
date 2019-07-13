<template>
  <div class="text-center" id="app">
    <h1>Word Translator</h1>
    <h5>Powered by VUE.js</h5>
    <TranslateForm @formSubmit = "translateText"></TranslateForm>
    <TranslateOutput v-text = "translatedText"></TranslateOutput>
  </div>
</template>

<script>

import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'

export default {
  name: 'app',
  components: {
    TranslateForm,
    TranslateOutput
  },
  data() {
    return {
      translatedText: ''
    }
  },
  methods: {
    translateText(text, language) {
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20190713T103314Z.3b00a52205f2d453.b7afd25351a798d164e9bf977fa0e30d69949fe4&lang=' +language+' &text=' +text).then((response) => {
        this.translatedText = response.body.text[0];
      })

    }
  }
  
}
</script>

<style>
body {
  background: #fefefe;
}
</style>
