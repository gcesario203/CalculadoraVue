<template>
    <button class="button" :class="{double,triple,operation}">
        {{label}}
    </button>
</template>

<script>
export default {
    props:{
        label:{},
        operation: {type:Boolean},
        double: {type:Boolean},
        triple: {type:Boolean}
    }
}
</script>

<style>
:root{
    --bg-button:#575454;
    --border-button: solid 1px rgb(212, 209, 209);
}
.button{
    color: white;
    font-size: 1.4em;
    background-color: var(--bg-button);
    border: none;
    outline: none;
    transition: 100ms;
}

.button:active{
    background-color: rgb(114, 105, 105);
    border-right: var(--border-button);
    border-bottom: var(--border-button);
}

.button.double{
    grid-column: span 2;
}

.button.triple{
    grid-column: span 3;
}

.button.operation{
    background-color: dodgerblue;
    color: white;
    transition: 100ms;
}

.button.operation:active{
    background-color: rgb(53, 142, 231);
}
</style>