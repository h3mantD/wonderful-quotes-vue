<template>
    <div class="row">
        <app-quote
            v-for="(q, index) in Qs"
            :key="(q, index)"
            @click.native="deleteQuote(index)"
        >
            {{ q }}
        </app-quote>
    </div>
</template>

<script>
import { eventBus } from "../main.js";
import Quote from "./Quote.vue";

export default {
    props: ["Qs"],

    methods: {
        deleteQuote(index) {
            eventBus.$emit("deleteQuote", index);
        },
    },

    components: {
        appQuote: Quote,
    },
};
</script>

<style scoped></style>
