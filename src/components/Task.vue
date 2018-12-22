<template>
<div>
    <ul>
    <input class=counter v-model="task" placeholder="追加するタスクを入力">
    <p>Add task: {{ task }}</p>
    <button  v-on:click="addNewTodo">タスクを追加</button>
        <li v-for="task in list" v-bind:key="task.id">
            <br>
            {{ task.id }} {{ task.name }} <button  v-on:click="addNewTodo">タスクを削除</button>
        </li>
    </ul>
</div>
</template>

<script>
export default {
  data () {
      return {
          //初期化
          task: '',
          list: [
              {id: 1, name: '課題掃除'},
              {id: 2, name: 'JavaFX'},
            ],
        };
    },
methods: {
    addNewTodo () {
      this.list.push({
        id: this.list.length + 1,
        name: this.task
      })
    },
    deleteTodo () {
        
    }
  },
}
</script>

<style scoped>
.counter {
    font-size: 26px;
    background-color: #dfd;

}
</style>