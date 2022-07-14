<script setup>
import HomeVue from './Home.vue';
import AboutVue from './About.vue';
import ContactVue from './Contact.vue'
</script>
<script>

const routes = {
    '/': HomeVue,
    '/about': AboutVue,
    '/contact':ContactVue
}


export default {
    data() {
        return {
            currentPath: window.location.hash
        }
    },
    computed: {
        currentView() {
            return routes[this.currentPath.slice(1) || '/'] || NotFound
        }
    },
    mounted() {
        window.addEventListener('hashchange', () => {
            this.currentPath = window.location.hash
        })
    }
}

</script>
<template>
    <div class="Nav">
        <nav class="navbar navbar-expand-lg bg-dark navbar-dark">
            <div class="container-fluid">
                <a class="navbar-brand" herf="#/">Home</a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                    data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent"
                    aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarSupportedContent">
                    <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                        <li class="nav-item">
                            <a href="#/"  class="nav-link active">Home</a>

                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#/about">About</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#/contact">Contact</a>
                        </li>
                    </ul>
                    <form class="d-flex" role="search">
                        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                        <button class="btn btn-outline-success" type="submit">Search</button>
                    </form>
                    
                </div>
            </div>
        </nav>
    </div>
                        <component :is="currentView" />
</template>


<style>
.Nav {
    width: 100vw;
}
</style>
