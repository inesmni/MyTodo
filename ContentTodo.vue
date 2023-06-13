<template>

    <div class="card my-2 items">

        <p>{{ tache }}</p>
        <button class="btn btn-success btn-delete" v-on:click="deleteItem">X</button>
    </div>
</template>

<script>

export default {
    name:"ContentTodo",
    props:['tache', 'deleteItem']
}
</script>

<style scoped>
.items{
    position: relative;
    font-size: 18px;
    padding: 20px 60px 20px 30px;
    height: 90px;
}

button {
    position: absolute;
    top: 0,5rem;
    right: 0,5rem;
}
</style>