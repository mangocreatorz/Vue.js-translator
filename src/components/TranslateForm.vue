<template>
  <div class="row" id="translateForm">
      <div class="col-md-6 col-md-offset-3">
    <form class="well" @submit="formSubmit">
        <input class="form-control" type="text" v-model="textToTranslate" placeholder="Enter a word">
        <select class="form-control" v-model="language">
            <option value="ru">Russian</option>
            <option value="es">Spanish</option>
            <option value="fr">French</option>
            <option value="da">Danish</option>

        </select>
        <br>
        <input class="btn btn-primary" type="submit" value="Translate">

    </form>
    <TranslateForm/>
    </div>
  </div>
</template>

<script>



export default {
  name: 'translateForm',
  data() {
      return {
          textToTranslate: '',
          language: ''
      }
  },
  created() {
      this.language = 'ru';
  },
  methods: {
      formSubmit(e) {
          this.$emit('formSubmit', this.textToTranslate, this.language);
          e.preventDefault();
      }
  }
  
  
}
</script>

<style>

</style>
