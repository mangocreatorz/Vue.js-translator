<template>
  <div id="translateOutput">
    <form>
        <h2 class="text-info">{{translatedText}}</h2>
    </form>
    <TranslateForm/>
  </div>
</template>

<script>



export default {
  name: 'translateOutput',
  props: ['translatedText']
    
  
}
</script>

<style>

</style>
