<template>
  <div id="app">
    <global-component></global-component>
    <local-component :item="items[1]"></local-component>
  </div>
</template>

<script>
  import LocalComponent from './components/local-component'

  export default {
    name: 'app',
    data: () => ({
    items: [{
        title: 'HTML5',
      }, {
        title: 'CSS3',
      }, {
        title: 'JavaScript',
      }, ],
    }),
    components: { LocalComponent }
  }
</script>
