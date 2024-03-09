<template>
    <div>
        <button @click="completeTask">X</button>
        {{ desc }}
    </div>
</template>

<script>
export default {
    props: {
        desc: String
    },
    methods: {
        completeTask() {
            this.$emit("task-completed");
        }
    }
}
</script>

<style scoped>
div {
    background: white;
    text-align: left;
    padding: 10px;
}
button {
    margin-right: 5px;
}
</style>