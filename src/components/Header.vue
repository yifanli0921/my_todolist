<template>
  <div class="todo-header">
    <h1>todos</h1>
    <input
        type="text"
        placeholder="what needs to be done?"
        v-model="todos"
        @keyup="addTodos" />
    <div class="todoItems">
      <TodoItems
          v-for="(item,index) in showList"
          :key="index"
          :itemid="item"
      ></TodoItems>
    </div>
    <todo-bottom v-show="todoList && todoList.length >0 " ></todo-bottom>
  </div>

</template>

<script>
import TodoItem from "./TodoItem.vue"
import TodoBottom from "./TodoBottom.vue"
import { useStore } from "vuex";
import { computed } from "vue"

export default ( {
  name: 'TodoList',
  components:{
    TodoItem,
    TodoBottom,
  },
  setup(props) {
    const store = useStore();
    const todos = computed( {
      get: () => store.state.todos,
    })
  }
})

</script>

<style scoped>
input {
  width: 560px;
  height: 28px;
  font-size: 14px;
  border: 1px solid #2c3e50;
  padding: 4px 7px;
}
 h1{
   font-size: 100px;
   font-weight: 100;
   margin-bottom: 20px;
}
input:focus {
  outline: none;
  border-color: #42b983;
  box-shadow: inset 0 1px 1px salmon,0 0 8px goldenrod;
}
.todoItems {
  width: 604px;
  display: block;
}

</style>
