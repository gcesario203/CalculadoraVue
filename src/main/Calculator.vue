<template>
    <div class="calculator">
        <Display :value="displayValue"></Display>
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

    data:function(){
        return{
            displayValue:"0",
            clearDisplay:false,
            operation:null,
            value:[0,0],
            current:0,
        }
    },
    components:{Button,Display},
    methods:{
        clearMemory(){
            Object.assign(this.$data, this.$options.data(   ))
        },
        setOperation(operation){
            if(this.current===0){
                this.operation = operation
                this.current = 1
                this.clearDisplay = true
            }else{
                const equals = operation === '='
                const currentOperation = this.operation

                try {
                    this.value[0] = eval(
                        `${this.value[0]}${currentOperation}${this.value[1]}`
                    )
                } catch (error) {
                    this.$emit('onError', error)
                }

                this.value[1] = 0

                this.displayValue = this.value[0]
                this.operation = equals?null:operation
            }
        },
        addDigit(n){
            if(n==='.' && this.displayValue.includes('.')){
                return
            }

            const clearDisplay = this.displayValue ==='0' || this.clearDisplay

            const currentValue = clearDisplay?'':this.displayValue

            const displayValue = currentValue + n

            this.displayValue = displayValue
            this.clearDisplay = false

            if(n!=='.'){
                const i = this.current
                const newValue = parseFloat(displayValue)
                this.value[i]=newValue
            }
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