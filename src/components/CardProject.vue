<script>
import { store } from '../store';

export default {
    name: 'CardProject',

    props: {
        project: Object,
    },

    data() {
        return {
            store,
        }
    },


}

</script>

<template>

    <div class="col-3 p-4">
        <div class="card p-2">
            <h4>
                {{ project.title }}
            </h4>

            <h5>
                {{ project.slug }}
            </h5>

            <p>
                {{ project.description }}
            </p>

            <p v-if="project.type">
                Type: {{ project.type.name }}
            </p>

            <div v-if="(project.technologies).length > 0">
                <p>
                    technologies:
                </p>
                <ul>
                    <li v-for="(tech, index) in project.technologies" :key="index">
                        {{ tech.name }}
                    </li>
                </ul>
            </div>

            <figure v-if="project.cover_image">
                <img :src="`${this.store.apiBase}/storage/${project.cover_image}`" alt="">
            </figure>

            <div class="btn btn-primary mt-3 text-white">
                <RouterLink :to="{ name: 'single-project', params: { slug: project.slug } }" class="router-btn">Go to
                    Project</RouterLink>
            </div>

        </div>
    </div>

</template>

<style lang="scss" scoped>
.card {
    img {
        max-width: 100%;
    }

    .router-btn {
        color: inherit;
        text-decoration: none;
    }
}
</style>