<template>
    <div>
        <button @click="increment">Increment by {{ incrementStep }}</button>
        <p>Count: {{ count }}</p>
    </div>
</template>

<script>
  export default {
    props: {
        incrementStep: {
            type: Number,
            default: 1
        }
    },
    data() {
        return {
            count: 0,
        }
    },
    methods: {
        increment() {
            console.log(typeof this.incrementStep)
            this.count += this.incrementStep;
        }
    }
  };
</script>