<template>
    <h1>Job details page</h1>
    <!-- <p>The job id is {{ $route.params.id }}</p> -->
    <p>The job id is {{ id }}</p>
</template>

<script>
export default {
    props : ['id'],
    //replace by  props: true in index.js
    // data() {
    //     return {
    //         //pass id like this to only use id in template
    //         id: this.$route.params.id
    //     }
    // }
}
</script>

<style>

</style>