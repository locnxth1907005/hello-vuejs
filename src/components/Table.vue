<template>
    <table>
        <thead>
        <tr>
            <th v-for="col in columns">{{ col.label }}</th>
        </tr>
        </thead>
        <tbody>
        <tr v-for="item in data">
            <td v-for="col in columns">
                <template v-if="col.field !== 'action'">
                    {{ item[col.field] }}
                </template>
                <template v-else>
                    <a href="javascript:void(0)">Edit</a> | <a href="javascript:void(0)">Delete</a>
                </template>
            </td>
        </tr>
        </tbody>
    </table>
</template>

<script>
    export default {
        props:{
            data:{
                type: Array,
                default: () => []
            },
            columns:{
                type: Array,
                default: () => []
            }
        },
        name: "Table"
    }
</script>

<style scoped>

</style>