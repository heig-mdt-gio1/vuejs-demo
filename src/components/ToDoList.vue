<template>
    <h1>Tasks</h1>
    <div class="container">
        <ToDoInput @task-added="addTaskTolist"/>
        <div class="tasks">
            <ToDoItem
                v-for="task, index in tasks"
                :desc="task"
                :key="index"
                @task-completed="removeTaskFromList(index)"/>
        </div>
    </div>
</template>

<script>
import ToDoItem from './ToDoItem.vue'
import ToDoInput from './ToDoInput.vue'

export default {
    components: {
        ToDoItem,
        ToDoInput
    },
    data() {
        return {
            tasks: ["A hardcoded task from list", "Another hardcoded task", "Yet another hardcoded task", "And one last hardcoded task"]
        };
    },
    methods: {
        addTaskTolist(newTaskDesc) {
            this.tasks.push(newTaskDesc);
        },
        removeTaskFromList(index) {
            this.tasks.splice(index, 1)
        }
    }
}
</script>

<style scoped>
.container {
    background: whitesmoke;
    max-width: 500px;
    margin: auto;
    border-radius: 5px;
    padding: 20px;
}

.tasks {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 10px;
}
</style>