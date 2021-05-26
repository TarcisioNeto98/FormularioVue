<template>
    <form method="get" id="formulario">
        <input type="text" name="nome" v-model="nome"/>
        <input type="checkbox" v-model="status"/>
        <input type="button"/>

        <div></div>
    </form>
</template>

<script>

export default {
    name: 'Formulario',
    data: {
        nome: "",
        status: false
    },
    methods:{
        clique: function(){
            alert("resident vil")
        }
    }
}

</script>

<style>
    #formulario{
        background-color: azure;
        width: 80%;
        margin-right: auto;
        margin-left: auto;
    }
</style>