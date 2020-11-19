<template>
    <header>
        <h1>Noroff VueApp</h1>    
    </header> 
</template>

<script>
export default {
    name: 'Header',
     
}
</script>

<style scoped>
    header {
        height: 100px;
        background-image: linear-gradient(to top, #0bb86d 0%, #40c59b 100%);
    }
    h1 {
        font-size: 48px;
        color: purple;
        text-align: center;
        line-height: 100px;
    }
</style>