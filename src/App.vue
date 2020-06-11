<template>
 <div id="app">
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

    background: linear-gradient(to right, rgb(223, 219, 8),rgb(156, 148, 31));
}

</style>