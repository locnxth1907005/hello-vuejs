<template>
    <div class="submit-btn">
        <p>
            <input type="submit" value="Submit" @click="callingParentComponentMethod">
            "OR"
            <input type="submit" value="Submit" v-on:click="callingParentComponentMethod">
        </p>
    </div>
</template>
<script>
    export default {
        name: "Child",
        methods: {
            // This method will call on click of submit button
            callingParentComponentMethod() {
                // emit the event and call the parent component
                this.$emit("setParentComponentDetails");
            }
        }
// props: ["cTitle", "cAbout", "cHome"]
    };
</script>

<style scoped>

</style>