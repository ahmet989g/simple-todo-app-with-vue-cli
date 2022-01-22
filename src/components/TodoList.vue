<template>
    <ul>
        <TodoListItem @delete-todo-item="$emit('delete-todo-item', $event)" v-for="todoItem in provideData.todoList" :key="todoItem.id" :item="todoItem" />
    </ul>
</template>
<script>
import TodoListItem from '@/components/TodoListItem'

export default{
    //props: ["myData"],
    inject: ["provideData"],
    components: {
        TodoListItem
    },
}
</script>
