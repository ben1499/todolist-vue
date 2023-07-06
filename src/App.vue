<template>
  <div id="app">
    <search-comp @item-submitted="handleData"></search-comp>
    <todo-item @item-removed="handleDelete" v-bind:items="items"></todo-item>
  </div>
</template>

<script>
import SearchComp from './components/SearchComp.vue'
import TodoItem from './components/TodoItem.vue'

export default {
  name: 'App',
  data() {
    return {
      items: []
    }
  },
  components: {
    'search-comp': SearchComp,
    'todo-item': TodoItem
  },
  methods: {
    handleData: function(data) {
      this.items.push(data);
    },
    handleDelete(position) {
      this.items.splice(position, 1);
    }
  }
}
</script>

<style> 
body {
  background-color: #eee;
  font-family: sans-serif;
}

#app {
  max-width: 30%;
  margin: 0 auto;
  margin-top: 50px;
  text-align: center;
  background-color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding-top: 20px;
  border-radius: 12px;
}
</style>
