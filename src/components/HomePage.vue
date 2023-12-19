<template lang="">
    <div class="background-top">
        <div></div>
    </div>
    <section id="one">
        <div class="introduction container">
            <p>Ahoj!</p>
            <p>Volám sa 
                <span class="name">Viktor</span>.
            </p>
            <p>Zaujímam sa o moderné</p>
            <p>
                <span class="technology">technológie </span>
                <span>a </span>
                <span class="code">programovanie</span>.
            </p>
        </div>  
    </section>
</template>

<style lang="scss">
    @import '../assets/variables.scss';

    .background-top {
        background: url(../../src/img/colorful-background.jpg);    
        background-position: center center;
        background-size: cover;
        width: 100%;
        height: 120%;
        position: absolute;
        z-index: 1;
        & div {
            position: relative;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, rgba(0, 0, 0, 1) 10%, rgba(0, 0, 0, 0) 65%);
            z-index: 2;
        }
    }

    #one {
        //background: radial-gradient(circle at bottom left, rgba(0, 0, 0, 1), rgba(0, 0, 0, 0));
        //background: linear-gradient(45deg, rgba(0, 0, 0, 1), rgba(0, 0, 0, 0) 65%);
        font-family: 'Orbitron', sans-serif;
        font-weight: 900;
        text-transform: uppercase;
        text-align: left;
        overflow: hidden;
        display: flex;
        flex-direction: column;
        justify-content: end;
        position: relative;
        z-index: 3;
    }

    .introduction {
        display: flex;
        flex-direction: column;
        justify-content: end;
        //margin-bottom: $container-margin;
        z-index: 2;
        color: aliceblue;
        padding: 1.5em 0;  
        & p {
            margin: 0.15em 0 0 0;
            font-size: 2em;
        }
        & .name {
            color: $yellow;
        }
        & .technology {   
            color: $red;
        }
        & .code {
            color: $blue;
        }
    }

    @media only screen and (max-width: 900px) {
        .introduction{
            & p {
                font-size: 1.5em;
            }
        }
    }

    @media only screen and (max-width: 600px) {
        .introduction{
            & p {
                font-size: 1.25em;
            }
        }
    }

    
    @media only screen and (max-width: 500px) {
        .introduction{
            & p {
                font-size: 1em;
            }
        }
    }
</style>