<template lang="">
    <section id="three">
        <div class="course-box container">
            <div class="course-header container">
                <h1>Kurzy, ktoré som absolvoval:</h1>
            </div>
            <div v-for="course in coursesData" 
                :key="course.name"
                class="course-box-item"
                :class="course.def">
                <div class="item-bg"></div>
                <div class="logo-and-name">
                    <img :src="course.image" :alt="course.name">
                    <h3><a :href="course.link" target="_blank">{{ course.name }}</a></h3>
                </div>
                <div class="description">{{ course.description }}</div>
            </div>
        </div>
    </section>
</template>

<script>
    import jsonData from '../data/course-data.json'

    export default {
        name: 'MyCourses',
        data() {
            return {
                coursesData: jsonData,
            }
        }
    }
</script>

<style lang="scss">
    @import '../assets/variables.scss';

    $basic-transition: all 0.5s ease;

    #three {
        font-family: "Montserrat", sans-serif;
        text-align: left;
        color: cornsilk;
    }

    .course-box {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        gap: 1em;
        padding-top: calc(1em + $navigation-height);
    }

    .course-header{
        display: flex;
        justify-content: center;
        align-items: center;
        & h1{
            margin: 0;
        }
    }

    .course-box-item {
        overflow: hidden;
        border-radius: 1.5em;
        padding: 1.25em;
        background-color: #121212;
        overflow: hidden;
        position: relative;
        top: 0;
        transition: $basic-transition;
        z-index: 3;
    }

    .course-box-item:hover .item-bg {
        transform: scale(10.5);
    }

    .course-box-item:hover .logo-and-name h3 a {
        text-decoration: underline;
    }

    .course-box-item:hover {
        top: 0.35em;
    }

    .logo-and-name {
        display: flex;
        position: relative;
        left: 0;
        z-index: 2;
        transition: $basic-transition;
    }

    .logo-and-name img {
        max-width: 60px;
        height: 60px;
        border-radius: 0.75em;
        transform: scale(1);
        transition: $basic-transition;
    }

    .logo-and-name h3 {
        font-size: 1.2em;
        margin: 0 0.75em;
        transition: $basic-transition;
    }

    .logo-and-name h3 a {
        color: cornsilk;
        text-decoration: none;
        transition: $basic-transition;
    }

    .description {
        display: flex;
        position: relative;
        top: 0;
        margin-top: 1em;
        font-size: 1em;
        z-index: 2;
        transition: $basic-transition;
    }

    .item-bg {
        height: 128px;
        width: 128px;
        position: absolute;
        top: -75px;
        right: -75px;
        border-radius: 50%;
        transition: $basic-transition;
    }

    .webrebel .item-bg {
        background-color: $red;
    }

    .oop .item-bg {
        background-color: $yellow;
    }

    .sass .item-bg {
        background-color: $purple;
    }

    .github .item-bg {
        background-color: $green;
    }

    .js-games .item-bg {
        background-color: $blue;
    }

    @media only screen and (max-width: 900px) {
        .course-box {
            grid-template-columns: 1fr 1fr;
        }
        .logo-and-name h3 {
            font-size: 1em;
            margin: 0 0.75em;
            transition: $basic-transition;
        }
        .description {
            font-size: 0.7em;
        }
    }

    @media only screen and (max-width: 600px) {
        .course-box {
            grid-template-columns: 1fr;
        }
    }
</style>