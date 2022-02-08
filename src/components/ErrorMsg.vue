<template>
    <dialog open>
        <slot></slot>
    </dialog>
</template>

<script>
    export default {
        name: 'ErrorMsg',
    }
</script>

<style scoped>
dialog{
    margin: 0;
    position: fixed;
    top: 20vh;
    left: 30%;
    width: 40%;
    background-color: #ffffff;
    box-shadow: 0px 2px 8px rgb(0, 0, 0, 0.26);
}
</style>