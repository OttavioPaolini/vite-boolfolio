<script>
import axios from 'axios';
import ProjectCard from './ProjectCard.vue';

export default{
    name: "AppMain",

    data(){
        return{
            urlLaravel: "http://127.0.0.1:8000",
            projects: [],

           
        };
    },

    created(){
        this.getProject();
    },


    methods: {
        getProject(){
            axios.get(`${this.urlLaravel}/api/projects`).then(resp =>{
                this.projects = resp.data.results;
                
            });
        }
    },

    components:{
        ProjectCard,

    } 
}
</script>

<template>
    <div class="container">
        <h1 class="text-center text-primary mb-4">I miei Progetti</h1>

        <div class="row justify-content-center">
            <div  v-for="project in projects" :key="project.id" class="col-11">
                <ProjectCard  :project="project"/>
            </div>
        </div>
    </div>
</template>