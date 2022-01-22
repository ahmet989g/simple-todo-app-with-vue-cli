<template>
    <TodoList />
    <ResultBar :itemLenght="provideData.todoList.length" />
</template>

<script>
import TodoList from "@/components/TodoList"
import ResultBar from "@/components/ResultBar"

export default{
    inject: ["provideData"],
    props: {
        todoList: {
        type: Array,
        required: true
        }
    },
    components: {
        TodoList,
        ResultBar
    },
}
</script>
