<template>
<div class="container">
  <h3 class="text-center">ToDo App</h3>
  <hr class="my-2" />
  <AddSection :addNewTodo="addNewTodo" />
  <ListSection/>
</div>
</template>

<script>
import AddSection from "@/components/AddSection"
import ListSection from "@/components/ListSection"
export default {
    components: {
        AddSection,
        ListSection
    },
    data(){
        return{
            provideData:{
                todoList : [
                    { id : 1, text : "ToDo Item #2.0" },
                    { id : 2, text : "ToDo Item #2.1" },
                    { id : 3, text : "ToDo Item #2.2" },
                    { id : 4, text : "ToDo Item #2.3" },
                    { id : 5, text : "ToDo Item #2.4" },
                    { id : 6, text : "ToDo Item #2.5" }
                ]
            }
        }
    },
    provide(){
        return{
            provideData: this.provideData,
            deleteItem: this.deleteItem
        }
    },
    methods : {
        deleteItem(todoItem){
            this.provideData.todoList = this.provideData.todoList.filter((t) => t != todoItem)
        },
        addNewTodo(todo){
            this.provideData.todoList.push({
                id : new Date().getTime(),
                text : todo
            });
        }
    }
}
</script>

