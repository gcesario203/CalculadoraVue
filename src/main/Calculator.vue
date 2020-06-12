<template>
    <div class="calculator">
        <Display value="2"></Display>
        <Button label="AC" triple @onClick="clearMemory"></Button>
        <Button label="/" operation @onClick="setOperation"></Button>
        <Button label="7" @onClick="addDigit"></Button>
        <Button label="8" @onClick="addDigit"></Button>
        <Button label="9" @onClick="addDigit"></Button>
        <Button label="*" operation @onClick="setOperation"></Button>
        <Button label="4" @onClick="addDigit"></Button>
        <Button label="5" @onClick="addDigit"></Button>
        <Button label="6" @onClick="addDigit"></Button>
        <Button label="-" operation @onClick="setOperation"></Button>
        <Button label="1" @onClick="addDigit"></Button>
        <Button label="2" @onClick="addDigit"></Button>
        <Button label="3" @onClick="addDigit"></Button>
        <Button label="+" operation @onClick="setOperation"></Button>
        <Button label="0" double @onClick="addDigit"></Button>
        <Button label="." @onClick="addDigit"></Button>
        <Button label="=" operation @onClick="setOperation"></Button>
    </div>
</template>

<script>
import Button from '../components/Button'
import Display from '../components/Display'

export default {
    components:{Button,Display},
    methods:{
        clearMemory(){
            console.log('limpar')
        },
        setOperation(operation){
            console.log('op' + operation)
        },
        addDigit(n){
            console.log(n)
        }
    }
}
</script>

<style>
.calculator{
    height: 330px;
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
    ;
}
</style>