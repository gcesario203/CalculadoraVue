<template>
    <div class="calculator">
        <Display></Display>
        <Button></Button>
        <Button></Button>
        <Button></Button>
        <Button></Button>
    </div>
</template>

<script>
import Button from '../components/Button'
import Display from '../components/Display'

export default {
    components:{Button,Display}
}
</script>

<style>
.calculator{
    height: 320px;
    width: 100%;
    max-width: 250px;
    background: linear-gradient(to left, rgb(20, 20, 20),rgb(77, 74, 74));
    border-radius: 9px;
    overflow: hidden;

    display: grid;
    grid-template-columns: repeat(4,25%);
    grid-template-rows: 1fr 48px 48px 48px 48px 48px;

    grid-template-areas:
        "display display display display" 
        "button button button button" 
        "button button button button" 
        "button button button button" 
    ;
}
</style>