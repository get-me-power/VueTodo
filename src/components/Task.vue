<template>
<div>
    <input :value="message" placeholder="追加するタスクを入力">
    <p>Message is: {{ message }}</p>
</div>
</template>

<script>
export default {
    name: "Count",
};
</script>

<style scoped>
.counter {
    font-size: 26px;
    background-color: #dfd;
}
</style>