<template>

<div class="container px-2">
    <h1 class="text-center mb-4">MYTODO</h1>

    <form>
        <div class="form-group">
            <label for="taches" class="form-label"> Ecrire une tache</label>
            <input class="form-control" type="text" id="taches" v-model="formData.tache">
        </div>

        <button class="btn btn-success my-3" v-on:click.prevent="createItem"> Enregistrer</button>

    </form>

    <ul>

        <li class="m-3" v-bind:key="index" v-for="(tache, index) in tabTaches">


            <ContentTodo v-bind:id="index" v-bind:tache="tache" v-bind:deleteItem="deleteItem"></ContentTodo>

        </li>
    </ul>
</div>




</template>

<script>

import ContentTodo from './ContentTodo.vue'

export default {
    name:"MyTodo",
    data(){
        return{
            formData:{
                tache:""
            },
            tabTaches: ['Html', 'CSS', 'Javascript', 'PHP']
        }
    },
    components:{
        "ContentTodo":ContentTodo,
    },
    methods:{

        createItem: function(){
            this.tabTaches.push(this.formData.tabTaches)

            this.formData.tache =""
        },
        deleteItem: function(e){
            this.tabTaches.splice(e.target.parentNode.id, 1)
        }
    }
}
</script>

<style scoped>
ul {
    list-style: none;
}
</style>