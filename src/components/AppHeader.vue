<script>
export default {
    name: 'AppHeader',
    data() {
        return {
            navigation: [
                {
                    label: 'Home',
                    routeName: 'home'
                },
                {
                    label: 'About-us',
                    routeName: 'about-us'
                },
                {
                    label: 'Projects',
                    routeName: 'projects'
                },
            ]
        }
    }
}
</script>

<template>
    <header>
        <nav class="navbar bg-dark navbar-expand-lg bg-body-tertiary">
            <div class="container-fluid">
                <router-link :to="{ name: navigation[0].routeName }"
                    class="navbar-brand text-primary text-white">BoolFolio</router-link>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                    data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent"
                    aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
            </div>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav">
                    <li class="nav-item text-white" v-for="(navItem, index) in navigation" :key="index">
                        <router-link :to="{ name: navItem.routeName }" class="nav-link" aria-current="page">{{
                            navItem.label
                        }}</router-link>
                    </li>
                    <!-- <li class="nav-item">
                        <a class="nav-link" href="http://127.0.0.1:8000/admin">Login</a>
                    </li> -->
                </ul>
            </div>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
a {
    color: inherit;
}
</style>