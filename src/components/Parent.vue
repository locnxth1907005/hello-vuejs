<template>
    <div>
        <Child @setParentComponentDetails="setDetailsForComponent" > </Child>
    </div>
</template>
<script>
    // Path of child component
    import { Child } from "./Child.vue";
    export default {
        name: 'Parent',
        components: {
            Child
        },
        methods: {
            // Called by child component
            setDetailsForComponent() {
                console.log("Calling from child component");
            }
        }
    }
</script>

<style scoped>

</style>