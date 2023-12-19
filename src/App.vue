<script setup>
    import NavigationBar from './components/NavigationBar.vue'
    import HomePage from './components/HomePage.vue'
    import AboutMe from './components/AboutMe.vue'
    import MyCourses from './components/MyCourses.vue'
    import Hobbies from './components/Hobbies.vue'
</script>

<template>
    <div>
        <NavigationBar/>
        <HomePage/>
        <AboutMe/>
        <MyCourses/>
        <Hobbies/>
    </div>
</template>

<style lang="scss">
    @import url("https://fonts.googleapis.com/css2?family=Lexend:wght@900&family=Montserrat:wght@500;700;900&family=Orbitron:wght@600;900&display=swap");
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;900&display=swap');
    @import './assets/variables.scss';

    html {   
        scroll-behavior: smooth;
    }

    body {
        background-color: $dark-background;
        margin: 0;
    }

    section {
        min-height: 100vh;
        //margin: 1em;
    }

    .container {
        margin: 0 1.5em;
    }
</style>
