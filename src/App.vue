<template>
  <SettingsProvider>
    <ThemeButton />
  </SettingsProvider>
</template>

<script>
  
  import SettingsProvider from './SettingsProvider.vue'
  import ThemeButton from './ThemeButton.vue'

  export default {
    name: 'App',
    components: { SettingsProvider, ThemeButton }
  }

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
