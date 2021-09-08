<template>
    <div>
        <p>I'm a Counter!</p>
        <button @click="increment">increment</button>
        <button @click="decrement">decrement</button>
        <p>{{ count }} times</p>
    </div>
</template>

<script>
export default {
    props: {
        initial_count: Number,
    },
    data() {
        return {
            count: this.initial_count
        };
    },
    methods: {
        increment() {
            ++this.count;
        },
        decrement() {
            --this.count;
        },
    }
};
</script>

<style>
</style>

