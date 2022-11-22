<template>
  <v-container fluid>
    <v-form >
      <v-file-input
        label="Selecione as Legendas"
        prepend-icon="mdi-message-text"
        append-icon="mdi-send"
        outlined 
        multiple 
        chips 
        v-model="files"
        @click:append="processSubtitles"        >

      </v-file-input>
    </v-form>
    <div class="pills">
      <Pill v-for="word in groupedWords" :key="word.name"  :name="word.name" :amount="word.amount"/>
    </div>
  </v-container>
</template>

<script>
import { ref } from 'vue'
import {icpRenderer} from 'electron'
import Pill from './PillComponent.vue'
export default {
  components:{
    Pill
  },
  setup(){
    const files = ref([])
    const groupedWords = ref([
      { name:'i', amount:1234},
      { name:'you', amount:900},
      { name:'he', amount:853}
    ])

    const processSubtitles = () =>{
       icpRenderer.send('process-subtitles', 'ola')
    }

    return {
      groupedWords,
      files,
      processSubtitles
    }
  }
}
</script>

<style>
  .pills{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }

</style>