<template>
    <h1>Jobs</h1>
    <div v-if="jobs.length">
        <div v-for="job in jobs" :key="job.id" class="job">
            <router-link :to="{ name: 'jobsDetails', params: { id:job.id }}">
                <h2> {{ job.title }}</h2>
            </router-link>
        </div>
    </div>
    <div v-else>
        <p>Loading Jobs ....</p>
    </div>

  
</template>

<script>
export default {
    data() {
        return {
            jobs: []
        }
    },
    mounted() {
        setTimeout(() => {
            fetch('http://localhost:3000/jobs')
            .then((res) => res.json())
            .then((data) => this.jobs = data)
            .catch(err => console.log(err.message))

        }, 1000)
    } 
}
</script>

<style>
    .job h2 {
        background: #f4f4f4;
        padding: 25px;
        cursor: pointer;
        color: #444;
        border-radius: 20px;
        margin: 10px auto;
        max-width: 600px;
    }
    .job h2:hover {
        background: #ddd;
    }
    .job a {
        text-decoration: none;
    }
</style>