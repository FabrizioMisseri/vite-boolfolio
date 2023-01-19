<script>
import axios from "axios";

export default {
    name: 'AppMain',

    data() {
        return {
            apiUrlProjects: 'http://127.0.0.1:8000/api/projects',
        }
    },

    created() {
        this.getProjects();
    },

    methods: {
        getProjects() {
            axios.get(this.apiUrlProjects).then(resp => {
                // console.log(resp);
                const data = resp.data.results;
                return data;
            })
        },
    }
}
</script>

<template>

    ciao
    ciao
</template>

<style lang="scss" scoped>

</style>
