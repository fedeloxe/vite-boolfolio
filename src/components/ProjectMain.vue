<script>
import axios from 'axios';
import ProjectCard from './ProjectCard.vue';
export default {
    name: "ProjectMain",
    components: {
        ProjectCard
    },
    data() {
        return {
            projects: [],
            loading: true,
            baseUrl: 'http://127.0.0.1:8000'
        }
    },
    methods: {
        getProjects() {
            this.loading = true;
            axios.get(`${this.baseUrl}/api/projects`).then((response) => {
                if (response.data.success) {
                    this.projects = response.data.results
                    this.loading = false;


                }
                else {

                }
            })
        }
    },
    mounted() {
        this.getProjects()
    }
}
</script>
<template>
    <div class="container">
        <div class="row">
            <div>
                <h2 class="text-center my-3">Boolpress</h2>
            </div>
            <div class="col-12">
                <div v-if="loading" class="d-flex justify-content-center my-4">
                    <div class="loader"></div>
                </div>
                <div v-else class="col-12 d-flex justify-content-center my-4 flex-wrap">
                    <div class="row">
                        <div class="col-3" v-for="project in projects" :key="project.id">
                            <ProjectCard :project="project" />
                        </div>

                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<style lang="scss" scooped>
.loader {
    border: 16px solid #f3f3f3;
    /* Light grey */
    border-top: 16px solid #3498db;
    /* Blue */
    border-radius: 50%;
    width: 120px;
    height: 120px;
    animation: spin 2s linear infinite;
}

@keyframes spin {
    0% {
        transform: rotate(0deg);
    }

    100% {
        transform: rotate(360deg);
    }
}
</style>