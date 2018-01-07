<template>
  <div id="app" class="container">
    <div class="todo-wrapper">
      <todo-header></todo-header>
      <div class="todo-content">
        <todo-report></todo-report>
        <todo-list :collection="listState.items"></todo-list>
      </div>
    </div>
  </div>
</template>
<script>
  import ListStore from '../data/store.js'
  import Header from './components/TodoHeader.vue';
  import TodoReport from './components/TodoReport.vue';
  import TodoList from './components/TodoList.vue';
  // 引用组件
  
  export default {
    data() {
      return {
        listState: ListStore.state
      }
    },
    components: {
      "todo-header": Header,
      "todo-list": TodoList,
      "todo-report": TodoReport
    }
  }
</script>
<style>
</style>