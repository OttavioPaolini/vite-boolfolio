<script>
export default{
    name: 'ProjectCard',

    data(){
        return{
            urlLaravel: "http://127.0.0.1:8000",
        }
    },

    props: {
        project: Object
    }
}
</script>

<template>
<div class="card" >
    <div class="card-body">
        <h2 >{{project.title}}</h2>
        <p v-if="project.type ">{{ project.type.name }}</p>
        <p v-else>Nessuna tipologia</p>
        <img class="w-50" v-if="project.cover_image" :src="`${urlLaravel}/storage/${project.cover_image}`" alt="">
        <p v-else>Nessuna Immagine Trovata</p>
    </div>
</div>

</template>


<style scoped>
</style>