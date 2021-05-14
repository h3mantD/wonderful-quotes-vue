<template>
    <div>
        <form>
            <div class="form-group">
                <input type="text" v-model="q" />
            </div>
            <div class="form-group">
                <button @click.prevent="addQuote">Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>
import { eventBus } from "../main.js";
export default {
    data() {
        return {
            q: "",
            quote: "",
        };
    },

    methods: {
        addQuote() {
            this.quote = this.q;
            eventBus.$emit("addQuote", this.quote);
        },
    },
};
</script>
