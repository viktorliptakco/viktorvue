<template lang="">
    <section :style="sectionStyle" id="two">
        <div class= "container about-me">
            <p>
                Vítam vás na mojej stránke!!!!!!! Som Viktor Lipták, a programovanie je mojou vášňou, ktorej som sa začal venovať pomerne nedávno. Mojou hlavnou oblasťou záujmu sú webové stránky, no moje portfólio sa neustále rozširuje o nové zručnosti.
            </p>
            <p>
                Na začiatku mojej cesty som objavil svet HTML a CSS, a postupne som pridával do svojho arzenálu aj SCSS a JavaScript. S pribúdajúcimi skúsenosťami som sa dostal k PHP a princípom objektovo orientovaného programovania. Nedávno som začal pracovať aj s JavaScriptovým frameworkom VUE, cez ktorý je vytvorená aj táto stránka.
            </p>
            <p>
                Väčšinu doterajších zručností som nadobudol vďaka kurzovému portálu <a href="https://skillmea.sk/online-kurzy" target="_blank">Skillmea.sk</a>. Často čerpám z dokumentácií konkrétnych programovacích jazykov, rozširujem svoju schopnosť vyhľadávať pomocou Google a Youtube a v neposlednom rade mi s tvorením kódu pomáha umelá inteligencia.
            </p>
            <p>
                V sekcii nižšie popisujem <a href="#three">konkrétne kurzy</a>, ktoré som doteraz absolvoval cez spomínanú stránku Skillmea.
            </p>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'AboutMe',
        data() {
            return {
                sectionStyle: {
                    background: 'linear-gradient(0deg, rgba(10, 10, 10, 1) 85%, rgba(10, 10, 10, 0) 100%)',
                },
            };
        },
        created() {
            window.addEventListener('scroll', this.handleScroll);
        },
        beforeDestroy() {
            window.removeEventListener('scroll', this.handleScroll);
        },
        methods: {
            handleScroll() {
                const scrollTop = window.scrollY;
                const height = window.innerHeight;
                const maxScroll = (document.documentElement.scrollHeight - height) / 2;
                const percent = scrollTop / maxScroll;
                const gradientStop = percent * 15 + 85;
                if (gradientStop < 100) {
                     this.sectionStyle.background = `linear-gradient(0deg, rgba(10, 10, 10, 1) ${gradientStop}%, rgba(10, 10, 10, 0) 100%)`;
                }
               
            },
        },
    };
</script>

<style lang="scss">
    @import '../assets/variables.scss';

    #two {
        font-family: "Montserrat", sans-serif;
        position: relative;
        z-index: 3;
        color: white;
    }

    .about-me {
        display: grid;
        grid-template-columns: 1fr;
        gap: 0.5em;
        //background-attachment: fixed;
        //background-color: rgb(10, 10, 10);
        padding: 0;
        padding-top: calc(1em + $navigation-height);
        & p {
            margin: 0.5em 0em;
            font-size: 1.3em;
            //background-color: rgb(221, 221, 221);
            color: white;
        }
        & .text {
            border-radius: 0.5em;
            padding: 0.5em;
            margin: 0 0 1em 0;
            background: rgba(26, 26, 117, 0.575);
        }
        & a {
            color: yellow;
            position: relative;
            top: 0;
            text-decoration: none;
            transition: all 0.25s ease-in-out;
        }
        & a:hover {
            top: -0.15em;
            border-bottom: 1px solid yellow;
        }
    }

    .card {
        width: fit-content;
        height: fit-content;
        padding: 1em;
        border-radius: 1em;
        background: rgb(17, 17, 17);
        text-align: center;
        & div {
            overflow: hidden;
            border-radius: 0.5em;
            background: linear-gradient(#22c1c3, #fdbb2d);
            & img {
                max-width: 15em;
                transition: all 0.45s;
                position: relative;
                scale: 1.3;
                top: 2em;
            }
            & img:hover {
                scale: 1.5;
                top: 3.5em;
            }
        }

    }

@media only screen and (max-width: 600px) {
    .about-me {
        & p {
            font-size: 0.8em;
        }
    }
}
</style>