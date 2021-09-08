<template>
    <div>
        <!-- PART 1: Pass in a "complete" prop here -->
        <Instructions v-bind:complete="true"/>
        <!-- PART 4: Modify the Show component to accept all of these props -->
        <div>
            Enter a new show:
        </div>
        <input id="new_name" v-model="new_name" placeholder="new show name" type="text">
        <button @click="submit" type="button">Submit</button>
        <Show
                v-for="show in shows"
                :key="show.id"
                :id="show.id"
                :name="show.name"
                :episodes_seen="show.episodes_seen"
                />
    </div>
</template>

<script>
import Instructions from "./Instructions.vue";
import Show from "./Show.vue";

export default {
    components: {
        Instructions,
        Show
    },
    data() {
        return {
            shows: [
                { id: 1, name: "Game of Thrones", episodes_seen: 0 },
                { id: 2, name: "Naruto", episodes_seen: 220 },
                { id: 3, name: "Black Mirror", episodes_seen: 3 }
            ],
            id_num: 4,
            new_name: null,
        };
    },
    methods: {
        submit() {
            if (this.new_name) {
                this.shows.push({ id: this.id_num, name: this.new_name, episodes_seen: 0});
                ++this.id_num;
            }
        }
    }
};
</script>

<style>
</style>


