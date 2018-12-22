<template>
<div>
    <ul>
    <input class=counter v-model="task" placeholder="追加するタスクを入力">
    <p>Add task: {{ task }}</p>
    <button  v-on:click="addNewTodo">タスクを追加</button>
        <li v-for="task in list" v-bind:key="task.id">
            <br>
            {{ task.id }} {{ task.name }}
            <select v-model="selected">
                <option v-for="option in options" v-bind:value="option.value">
                    {{ option.text }}
                </option>
            </select>
            <button  v-on:click="deleteTodo">タスクを削除</button>

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
            ],
          selected: '',
          options: [
              { text: '優先度: 低い', value: 'A' },
              { text: '優先度: 中程度', value: 'B' },
              { text: '優先度: 高い', value: 'C' }
            ],
        };
    },
methods: {
    addNewTodo () {
      this.list.push({
        id: this.list.length + 1,
        name: this.task,
        //priorityは優先度
        priority: this.task
      })
    },
    deleteTodo () {
        this.list.pop({
            id: this.list.length - 1
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