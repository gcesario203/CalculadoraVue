<template>
 <div id="app">
     <h1>Ola mundo/VUe</h1>
 </div>
</template>

<script>
export default {

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