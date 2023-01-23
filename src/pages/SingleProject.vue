<script>
import axios from 'axios';
import { store } from '../store';

export default {
    name: 'SingleProject',

    data() {
        return {
            store,
            project: {},
        }
    },

    computed: {
        category() {
            return this.project.category ? this.project.category.name : 'Nessuna categoria';
        }
    },

    created() {
        const slug = this.$route.params.slug;
        axios.get(`${this.store.apiUrlProjects}/${slug}`).then(resp => {
            const data = resp.data;
            //console.log(data);
            if (data.success) {
                this.project = data.project;
            } else {
                this.$router.push({ name: 'not-found' });
            }
        });

    },
}
</script>

<template>

    <div class="container">
        <h1 class="mt-3 text-center">{{ project.title }}</h1>
        <h5 class="text-center mt-2 text-uppercase text-primary">{{ category }}</h5>
        <img v-if="project.cover_image" :src="`${store.apiBase}/storage/${project.cover_image}`" alt="">
        <div v-else class="text-center mt-4">Nessuna immagine</div>

        <p>{{ project.description }}</p>
    </div>

</template>

<style lang="scss" scoped>

</style>