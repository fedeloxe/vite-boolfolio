<script>
export default {
    props: {
        project: Object
    },
    data() {
        return {
            baseUrl: 'http://127.0.0.1:8000'
        }
    },

}
</script>
<template >
    <div>
        <div class="card my-3">
            <div class="card-img-top">
                <img class="img-fluid"
                    :src="project.cover_image
                        != null ? `${this.baseUrl}/storage/${project.cover_image}` :
                        'https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExZGZmZTBiMDU4OTQyY2FlODQxNGMwNzFmNjEzZmM2NTk0YTU0NGM2OSZjdD1n/xT5LMtQcg52JMYfPzO/giphy.gif'">
            </div>
            <div class="card-title">
                <h5>{{ project.title }}</h5>
            </div>
            <div class="card-text">
                {{ project.content }}

            </div>

        </div>
    </div>
</template>
<style lang="">
    
</style>