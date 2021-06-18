<template>
    <div>
        {{ titleConverted }} <br>
        <Table :columns="columns" :data="students"/>
    </div>
</template>

<script>
    import Table from "../components/Table";

    export default {
        name: "Student",
        components:{
            Table
        },
        data(){
            return {
                title: 'student management',
                students: [],
                columns: [
                    {
                        label: 'Id',
                        field: 'id',
                    },
                    {
                        label: 'Full Name',
                        field: 'fullName',
                    },
                    {
                        label: 'Email',
                        field: 'email',
                    },
                    {
                        label: 'Status',
                        field: 'status',
                    },
                    {
                        label: 'Created At',
                        field: 'createdAt',
                    },
                    {
                        label: 'Action',
                        field: 'action',
                    },
                ]
            }
        },
        mounted() {
            this.loadStudent()
        },
        methods: {
            loadStudent(){
                fetch('http://localhost:8081/api/students')
                    .then(response => response.json())
                    .then(data => this.students = data);
            }
        },
        computed: {
            titleConverted(){
                return this.title.toUpperCase()
            }
        }
    }
</script>

<style scoped>
    .error{
        color: red;
    }
</style>