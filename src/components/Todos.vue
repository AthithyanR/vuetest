<template>      

    <div class="row">
        <div v-bind:key="todo.id" v-for="todo in todos">
            <div class="col s12 m6">
                <div class="card">
                    <div class="card-content blue lighten-5">
                        <span class="text"> {{todo.title.charAt(0).toUpperCase() + todo.title.slice(1)}} </span>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>

<script>
export default {
    name:"Todos",
    props: ["todos"]
}
</script>

<style scoped>
    .row{
        margin-top: 2rem;
    }
    .text{
        font-family: 'Poppins';
        font-weight: 500;
    }
    .card-panel{
        text-align: center;
    }
</style>