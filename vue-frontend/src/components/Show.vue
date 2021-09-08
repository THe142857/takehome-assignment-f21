<template>
    <!-- PART 4: Add your code here -->
    <div>
        Counter for {{ name }}:
        <Counter :initial_count="episodes_seen" />
    </div>
</template>

<script>
// PART 4: Add your code here
import Counter from "./Counter.vue";

export default {
    name: "Show",
    props: {
        id: Number,
        name: String,
        episodes_seen: Number,
    },
    components: {
        Counter,
    }
};
</script>

<style>
</style>
