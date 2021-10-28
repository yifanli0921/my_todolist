<template>
 <div>
   <input type="checkbox"
          :class="{checkbox:true,notshow:active}"
          @click="completeTodos(item.id)" :checked="item.state === 'completed'" />
   <span :class="{isCompleted:item.state === 'compelted'}" @click="completeTodos(item.id)">{{item.value}}</span>
   <button icon="el-icon-close" circle @click="deleteTodos(item.id)"></button>
 </div>
</template>

<script>
import { useStore } from "vuex";
import { computed } from "vue";

export default {
  name: "TodoItem",
  props:["item"],
  setup() {
    const store = useStore();
    const deleteTodos = (id) => {
      console.log("点击删除");
      store.commit("deleteTodos",id);
    };
    const completeTodos = (id) => {
      store.commit("completeTodos",id);
    };
    const active = computed(() => {
      return store.state.active;
    })
    return {
      deleteTodos,
      completeTodos,
      active
    }
  }
}
</script>

<style scoped>
div {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 60px;
  border: 1px solid burlywood;
  box-shadow: 5px 5px 5px burlywood;
}
.el-button {
  margin-left: 10px;
}
.isCompleted {
  text-decoration: line-through;
  color: #42b983;
}
span {
  display: inline-block;
  width: 80%;
}
.checkbox {
  width: 10%;
  border-radius: 100%;
}

.notshow {
  opacity: 0;
}

</style>
<!--<template>-->
<!--  <div>-->
<!--    <input type="text"-->
<!--           class="todo-input"-->
<!--           placeholder="Todo List goes here"-->
<!--           v-model="newTodo"-->
<!--    />-->
<!--    <div v-for="todo in todos" :key="todo.id" class="todo-item">-->
<!--      {{todo.title}}-->
<!--    </div>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  name: "todo-list",-->
<!--  data(){-->
<!--    return {-->
<!--      newTodo:'',-->
<!--      todos: [-->
<!--        {-->
<!--          'id':1,-->
<!--          'title':'Finish Todo List',-->
<!--          'completed' :false,-->
<!--        },-->
<!--        {-->
<!--          'id':2,-->
<!--          'title':'Work Hard',-->
<!--          'completed' :false,-->
<!--        }-->

<!--      ]-->
<!--    }-->
<!--  }-->
<!--}-->
<!--</script>-->

<!--<style lang="scss">-->
<!--.todo-input {-->
<!--  width: 100%;-->
<!--  padding: 10px 18px;-->
<!--  font-size: 18px;-->
<!--  border-color: #42b983;-->
<!--}-->


<!--</style>-->
