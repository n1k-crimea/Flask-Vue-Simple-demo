<template>
    <div id="app">
        <ul>
            <li v-for="l in languages">{{ l }}</li>
        </ul>
    </div>
</template>

<script>
    import axios from 'axios';
    export default {
        name: 'app',
        data() {
            return {
                    languages: []
            }
        },
        created() {
            axios.get("/api/languages").then(r => {
                   this.languages = r.data.languages
            })
        }
    }
</script>

<style>

</style>
