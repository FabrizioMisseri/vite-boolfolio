<script>

export default {
    name: 'CardProject',

    props: {
        project: Object,
    },

    data() {
        return {

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
                <img :src="`http://127.0.0.1:8000/storage/${project.cover_image}`" alt="">
            </figure>

        </div>
    </div>

</template>

<style lang="scss" scoped>
.card {
    img {
        max-width: 100%;
    }
}
</style>