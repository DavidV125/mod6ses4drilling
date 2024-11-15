<script>

export default{
    props: {
        mensaje: String
}}

</script>


<template>
    <div class="principal">
        <h2 v-html="mensaje"></h2>

    </div>

</template>

<style scoped>
    h2{
        color: black;
    }
    p{
        font-size:larger;
    }
    .principal{
        background-color: greenyellow;
        margin:2%;
    }
</style>