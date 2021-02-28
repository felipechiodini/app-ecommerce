<template>
    <div class="container-fluid">

        <div class="row mb-2" v-for="(job, key) in jobList" :key="key">
            <div class="col-auto border border-dark rounded">
                <p>Nome: {{ job.name }}</p>
                <p>Atividades: {{ job.activities }}</p>
                <p>Cidade: {{ job.address.city }}</p>
                <p>Diferenciais: {{ job.differential }}</p>
                <p>Requisitos: {{ job.requirements }}</p>
            </div>
        </div>

        <div class="row d-flex justify-content-around align-items-end bg-info">

            <div class="col-auto">
                <span>dawdwad</span>
            </div>
            <div class="col-auto">
                <span>dawdwad</span>
                
            </div>
            <div class="col-auto">
                <span>dawdwad</span>
                
            </div>
            <div class="col-auto">
                
                <span>dawdwad</span>
            </div>

        </div>


    </div>
</template>

<script>
import axios from 'axios'
import Footer from '../components/Footer'

export default {
    metaInfo: {
        title: 'Trabalhe Conosco',
    },

    components: {
        Footer,
    },

    mounted() {
        this.reloadList()
    },

    data: () => {
        return {

            jobList: []

        }
    },  

    methods: {

        reloadList() {
            const vm = this
            axios({
                method: 'GET',
                url: 'http://localhost:3000/job',
            }).then((response) => {
                this.jobList = response.data
            })
        },

    }

}
</script>
