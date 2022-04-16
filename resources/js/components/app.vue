<template>
    <div class="todoListContainer">
        <div class="heading">
            <h2 id="title">Todo List</h2>
            <addTodoForm></addTodoForm>
        </div>
        <listView></listView>
    </div>
</template>>

<script>
import addTodoForm from "./addTodoForm.vue"
import listView from "./listView.vue"

export default ({
    components: {
        addTodoForm,
        listView
    }
})
</script>

<style scoped>
.todoListContainer {
    width: 350px;
    margin: auto;
}

.heading {
    background: #e6e6e6;
    padding: 10px;
}

#title {
    text-align: center;
}
</style>