<template>
    <div v-if="job">
        <h1>Job details page</h1>
        <!-- <p>The job id is {{ $route.params.id }}</p> -->
        <p>The job id is {{ id }}</p>
        <p> {{ job.title }} </p>
        <p> {{ job.details }} </p>
    </div>
    <div v-else>
        <p>Loading Job Details</p>
    </div>
</template>

<script>
export default {
    props : ['id'],
    data() {
        return {
            job: null
        }
    },
    mounted() {
        setTimeout(() => {
            fetch('http://localhost:3000/jobs/' + this.id)
            .then((res) => res.json())
            .then((data) => this.job = data)
            .catch(err => console.log(err.message))
     
        }, 1000);
    }
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