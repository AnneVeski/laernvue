<template>
<div>
  <div class="tabs is-centered is-large">
    <ul>
      <li v-for="(item,index) in items"
      :key="index"
      :class="{'is-active': index === active}"
      @click="active = index">
        <a>{{item.title}}</a>
      </li>
    </ul>
  </div>
  <section class="section">
    <component :is="items[active].componentName"></component>
  </section>
</div>
</template>

<script>
import ApiExample from './ApiExample.vue'
import ClickerExample from './ClickerExample.vue'
import ModalExample from './ModalExample.vue'
import RickAndMortyExample from './RickAndMortyExample.vue'

import ToDoExample from './ToDoExample.vue'


export default {
  components: { ModalExample, ToDoExample, ClickerExample, ApiExample, RickAndMortyExample, RickAndMortyExample},
    data(){
      return {
        active: 0,
        items: [
          {title:'Rick and Morty Example', componentName:'RickAndMortyExample'},
          {title:'Api Example', componentName:'ApiExample'},
          {title:'Clicker Example', componentName:'ClickerExample'},
          {title:'Modal Example', componentName:'ModalExample'},
          {title:'ToDo Example', componentName:'ToDoExample'},
        ]
      }
    }
}
</script>

<style>

</style>