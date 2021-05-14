<template>
    <div class="col-sm6 col-md-4 col-lg-3">
        <div class="quote-body quote">
            <slot></slot>
        </div>
    </div>
</template>

<script>
import { eventBus } from "../main.js";

export default {
    data() {
        return {};
    },

    methods: {},
};
</script>

<style scoped>
.quote-body {
    text-align: center;
    font-family: "Arizonia", cursive;
    font-size: 30px;
    border: 2px ridge;
    border-radius: 25px;
    padding: 20px;
    margin-bottom: 15px;
}

.quote {
    cursor: pointer;
    word-wrap: break-word;
}

.quote:hover {
    color: chocolate;
    background-color: rgba(128, 128, 128, 0.248);
}
</style>
