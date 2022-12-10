<template>
    <div class="backdrop" @click.prevent="closeModel">
        <div class="modal" :class="{ Sale: theme ==='Sale'}">
            <h1>{{ header}}</h1>
            <p>{{ text}}</p>
        
        </div>
    </div>
</template>
<script>
export default {
    props : ['header','text','theme'],
    methods: {
        closeModel(){
            this.$emit('close')
        }
    }
}
</script>
<style scoped>
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius:  10px;
}
.backdrop {
    top: 0;
    position: fixed;
    background:  rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;

}
h1{
    color: aqua;
    border: none;
    padding: 0;
}
.modal p{
font-style: normal;
}
.modal.Sale {
    background: crimson;
 color: white;
}
.modal.Sale h1{
    color: white;
}
</style>