<template>
<div>
    <ul>
    <input class=counter v-model="task" placeholder="追加するタスクを入力">
    <p>Add task: {{ task }}</p>
    <button  v-on:click="addNewTodo">タスクを追加</button>
    <!-- brは改行 -->
    <br>
    <span>Picked: {{ picked }}</span>
        <li v-for="task in list" v-bind:key="task.id">
            {{ task.id }} {{ task.name }}
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