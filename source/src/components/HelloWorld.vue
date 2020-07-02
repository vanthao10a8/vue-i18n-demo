<template>
  <div>
    <select v-model="currentLocale">
      <option v-for="locale in locales" v-bind:value="locale.id" v-bind:key="locale.id">{{locale.name}}</option>
    </select>
    <p>{{$t('Hello')}}</p>
  </div>
</template>

<script>
export default {
  data: function(){
    return{
      currentLocale : 'en',
      locales: [ {id: 'en', name: 'English'}, {id: 'vi', name: 'Viet Nam'}]
    }
  },
  watch : {
    currentLocale: function(){
      this.$i18n.locale = this.currentLocale;
    }
  }
}
</script>

<style>

</style>