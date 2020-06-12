<template>
 <div id="app">
     <h1>Calculadora Vue</h1>
     <Calculator></Calculator>
 </div>
</template>

<script>
import Calculator from './main/Calculator'
export default {
    components:{Calculator}
}
</script>

<style>
@font-face{
    font-family: 'RobotoMono';
    src: url("./fonts/RobotoMono-Thin.ttf");
}

*{
    color: black;
    font-family: 'RobotoMono',monospace;
}
body{
    margin: 0;
}

#app{
    display: flex;
    flex-direction: column;
    height: 100vh;
    justify-content: center;
    align-items: center;
    text-align: center;
    color: white;

    background: linear-gradient(to right, rgb(250, 250, 248),rgb(131, 131, 129));
}

</style>