<template>
  <div class="row">
  <character v-for="c in dataStore.characters.data.results" :key="c.id" :char="c"></character>
  </div>
</template>

<script>
  import {Store} from '@/Store.js'
  import Character from '@/components/Character/Character'
  export default {
    name: 'list',
    components: {
      character: Character,
    },
    data(){
      return {
        dataStore: Store.datas,
      }
    },
    created(){
      this.$Progress.start()
      Store.loadDatas();
       console.log(this.dataStore.characters)
    }
  }
</script>

<style scoped>

</style>
