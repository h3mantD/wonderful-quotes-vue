<template>
    <div class="container">
        <br />
        <quote-bar :ql="Qs.length"></quote-bar>
        <p>Add new quote</p>
        <add-quote></add-quote>
        <p>Following are the quotes</p>
        <quote-grid :Qs="Qs"></quote-grid>

        <div class="alert alert-primary" role="alert">
            Info: Click on the quote to delete it!!!
        </div>
    </div>
</template>

<script>
import { eventBus } from "./main.js";
import QuoteBar from "./components/QuoteBar.vue";
import AddQuote from "./components/AddQuote";
import QuoteInsert from "./components/Quote.vue";
import QuoteGrid from "./components/QuoteGridd.vue";

export default {
    data() {
        return {
            Qs: ["first quote", "second quote"],
            quote: "",
            maxQ: 10,
        };
    },

    methods: {
        addQuote(quote) {
            eventBus.$emit("updateBar", this.Qs.length);
            if (this.Qs.length < 10) this.Qs.push(quote);
            else alert("To add new quotes delete some previous quotoes!!!");
        },
    },

    components: {
        quoteBar: QuoteBar,
        addQuote: AddQuote,
        quoteGrid: QuoteGrid,
        quoteInsert: QuoteInsert,
    },

    created() {
        eventBus.$on("addQuote", (quote) => {
            this.addQuote(quote);
        });

        eventBus.$on("deleteQuote", (index) => {
            this.Qs.splice(index, 1);
        });
    },
};
</script>

<style></style>
