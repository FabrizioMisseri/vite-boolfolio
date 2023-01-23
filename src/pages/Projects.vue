<script>
import axios from "axios";
import CardProject from "../components/CardProject.vue";
import { store } from "../store";

export default {
    name: 'Projects',

    components: {
        CardProject,
    },

    data() {
        return {
            store,
            projectsArray: [],
        }
    },

    created() {
        this.getProjects();
    },

    methods: {
        getProjects() {
            axios.get(this.store.apiUrlProjects).then(resp => {
                // console.log(resp);
                this.projectsArray = resp.data.results;
                // console.log(this.projectsArray);
            })
        },
    }
}
</script>

<template>
    <div class="wrapper">
        <div class="container">
            <div class="row">

                <CardProject v-for="(project, index) in projectsArray" :project="project" :key="index" />

            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.wrapper {
    background-color: rgb(142, 142, 255);
    width: 100%;
    height: 100%;
}
</style>
