<template>
    <div>
        <form method="get" id="formulario">
            <label>Nome: </label><input type="text" name="nome" v-model="nome"/>
            <label> Status: </label><input type="checkbox" v-model="status"/>
            <input type="button" v-on:click="clique()" value="Criar"/>
        </form>
        <table>
            <thead>
                <th>id</th>
                <th>nome</th>
                <th>status</th>
            </thead>
            <tbody>
                <tr v-for="usuario in usuarios" v-bind:key="usuario.getId">
                    <td>{{usuario.id}}</td>
                    <td>{{usuario.nome}}</td>
                    <td>{{usuario.status}}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>

function Usuario(nome, status, id){
    this.nome = nome;
    this.status = status;
    this.id = id;

    this.getNome = function(){
        return this.nome;
    }

    this.getStatus = function(){
        return this.status;
    }

    this.getId = function(){
        return this.id;
    }
}

export default {
    name: 'Form',
    data: function() {
        return {
            nome: "",
            status: false,
            usuarios: [],
            id: 0
        };
    },
    methods:{
        clique (){
            var usuario = new Usuario(this.nome, this.status, this.id);
            this.usuarios.push(usuario);
            this.id++;
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