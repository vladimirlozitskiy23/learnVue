<template>
  <div id="App">
    <!-- //можно писать такой тэг, todos-list придумываем сами можно написать что угодно
    //если состоит из двух слов то в атрибутах используем кебаб кейс
    // v-bind: нужно использовать чтобы свойство todos передалось как массив, если
    //этого не сделать то передастся просто строка -->
    <TodoList :todos="todos" @delete-todo="deleteTodo"/>
  </div>

</template>

<script>

import TodoList from './components/TodoList.vue'

export default {
  name: 'App',
  // data должна быть в виде функции и возвращать наши свойства
  data() {
    return {
        todos: ['ремонт','завтрак', 'обед']

    }
  },
  // регистрируем
  components: {
    TodoList
  },
  methods: {
    deleteTodo(index){
      this.todos.splice(index, 1)
    }
  }
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
