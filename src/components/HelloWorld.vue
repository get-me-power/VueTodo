<template>
<div>
  <task></task>
  <!-- 標準入力を受け取るようにした -->
  <input v-model="msg" placeholder="タスクを入力してね">
  <p>Message is: {{ msg }}</p>
</div>

</template>

<script>
import Task from "./Task";
export default {
  
  components: {
    //Taskというdomを作成
    task: Task
  },
  data () {
    return {
      msg: ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
