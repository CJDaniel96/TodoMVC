<template>
    <div class="todoListContainer">
        <div class="heading">
            <h2 id="title">Todo List</h2>
            <addTodoForm v-on:reloadlist="getList()"></addTodoForm>
        </div>
        <listView :items="item" v-on:reloadlist="getList()"></listView>
    </div>
</template>>

<script>
import addTodoForm from "./addTodoForm.vue"
import listView from "./listView.vue"

export default ({
    components: {
        addTodoForm,
        listView
    },
    data: function () {
        return {
            item: []
        }
    },
    methods: {
        getList () {
            axios.get('api/todo')
            .then(response => {
                this.items = response.data
            })
            .catch(error => {
                console.log( error );
            })
        }
    },
    created() {
        this.getList();
    },
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