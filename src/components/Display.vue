<template>
  <div class="display">
      {{value}}
  </div>
</template>

<script>
export default {
    props:['value']
}
</script>

<style>
.display{
    width: 200px;
    max-width: 100%;
    margin: 5px;
    font-size: 2em;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-end;
    color: teal;
    padding: 20px;
    border-radius: 8px;
    background:whitesmoke;
    overflow: hidden;

    grid-area: display;
}
</style>