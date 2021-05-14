<template>
    <div class="progress bar" style="height: 40px;">
        <div
            class="progress-bar"
            role="progressbar"
            :style="{ width: ql * 10 + '%' }"
            aria-valuenow="25"
            aria-valuemin="0"
            aria-valuemax="10"
        >
            {{ ql }}
        </div>
    </div>
</template>

<script>
import { eventBus } from "../main.js";
export default {
    props: ["ql"],
    data() {
        return {
            //ql: this.Qs.length,
        };
    },

    created() {
        eventBus.$on("updateBar", (length) => {
            if (this.ql <= 10) this.ql = length;
        });
    },
};
</script>

<style scoped></style>
