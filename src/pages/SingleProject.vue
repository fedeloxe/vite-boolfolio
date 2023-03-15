<script>
import axios from 'axios';
import ProjectCard from '../components/ProjectCard.vue';
export default {
    name: 'SingleProject',
    components: {
        ProjectCard
    },
    data() {
        return {
            project: [],
            loading: true,
            baseUrl: 'http://127.0.0.1:8000'
        }
    },
    methods: {
        getProject() {
            this.loading = true;
            axios.get(`${this.baseUrl}/api/projects/${this.$route.params.slug}`).then((response) => {
                if (response.data.success) {
                    this.project = response.data.project;
                    this.loading = false;
                } else {
                }
            });
        }
    },
    mounted() {
        this.getProject()
    }
}
</script>
<template >
    <div>
        <div class="container">
            <div class="row my-4">

                <div class="col-6">
                    <img class="img-fluid rounded-1"
                        :src="project.cover_image
                            != null ? `${this.baseUrl}/storage/${project.cover_image}` :
                            'https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExZGZmZTBiMDU4OTQyY2FlODQxNGMwNzFmNjEzZmM2NTk0YTU0NGM2OSZjdD1n/xT5LMtQcg52JMYfPzO/giphy.gif'">

                </div>
                <div class="col-6">
                    <h2>{{ project.title }}</h2>
                    <span>{{ project.content }}</span>
                </div>

            </div>

        </div>

    </div>
</template>
<style lang="">
    
</style>