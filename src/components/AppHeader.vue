<script>
export default {

}
</script>
<template >
    <div class="ms-2">
        <nav class="navbar navbar-expand-lg navbar-light bg-light">
            <a class="navbar-brand" href="#">Navbar</a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup"
                aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
                <div class="navbar-nav">
                    <h2 class="nav-item nav-link active" href="#"><router-link to="/" class="nav-link">Home</router-link>
                    </h2>
                    <h2 class="nav-item nav-link" href="#"><router-link to="/portfolio"
                            class="nav-link">Portfolio</router-link>
                    </h2>
                </div>
            </div>
        </nav>
    </div>
</template>
<style lang="">
    
</style>