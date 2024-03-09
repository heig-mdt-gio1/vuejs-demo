<template>
    <div class="container">
        <input v-model="newTaskDesc" @input="errorMessage = ''"/>
        <button v-on:click="addTask">Add Task</button>
    </div>
    <ErrorPopup v-if="errorMessage.length > 0">
        {{ errorMessage }}
    </ErrorPopup>
</template>

<script>
import ErrorPopup from "./ErrorPopup.vue";

export default {
    components: {
        ErrorPopup
    },
    data() {
        return {
            errorMessage: "",
            newTaskDesc: ""
        }
    },
    methods: {
        addTask() {
            if (this.newTaskDesc.length == 0) {
                this.errorMessage = "Cannot add an empty task";
                return;
            } else {
                this.errorMessage = "";
            }
            console.log("Trying to add a task with description : " + this.newTaskDesc)
            this.$emit("task-added", this.newTaskDesc)
        }
    }
}
</script>

<style scoped>
.container {
    display: grid;
    width: 100%;
    grid-template-columns: 1fr 0fr;
    grid-gap: 10px;
}
.container button {
    white-space: nowrap;
}
</style>