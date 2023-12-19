<template lang="">
    <div>
        <nav ref="NavigationBar">
            <ul class="container">
                <li>
                    <a href="#one" class="one" :class="{ 'active': activeSection === 'one' }">Domov</a>
                </li>
                <li>
                    <a href="#two" class="two" :class="{ 'active': activeSection === 'two' }">O mne</a>
                </li>
                <li>
                    <a href="#three" class="three" :class="{ 'active': activeSection === 'three' }">Kurzy</a>
                </li>
                <li>
                    <a href="#four" class="four" :class="{ 'active': activeSection === 'four' }">Hobby</a>
                </li>
            </ul>
            <ul class="container contact">
                <li>
                    <a href="tel:+421944605452">
                        <i class="bi bi-telephone-fill"></i>
                    </a>
                </li>
                <li>
                    <a href="mailto:victor.liptak@gmail.com">
                        <i class="bi bi-envelope-fill"></i>
                    </a>
                </li>
            </ul>
        </nav>
    </div>
</template>

<script>
    export default {
        name: 'NavigationBar',
        data() {
            return {
                activeSection: 'one', // Reaktívna premenná pre aktívnu sekciu
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
                const sections = document.querySelectorAll('section');
                const currentSection = [...sections].find(section => {
                    const offset = section.offsetTop - 10;
                    return window.scrollY >= offset && window.scrollY < offset + section.offsetHeight;
                });
        
                this.activeSection = currentSection ? currentSection.id : '';

                // Ak je scrollovanie väčšie ako 50px, použi nové pozadie, inak ponechaj pôvodné
                const NavigationBar = this.$refs.NavigationBar;
                const scrollTop = window.scrollY;

                if (scrollTop >= 50) {
                    NavigationBar.style.backgroundColor = 'rgba(0, 0, 0, 0.8)';
                } else {
                    NavigationBar.style.backgroundImage = 'linear-gradient(0deg, rgba(0, 0, 0, 0), rgba(0, 0, 0, 1))';
                    NavigationBar.style.backgroundColor = 'rgba(0, 0, 0, 0)';
                }
            },
        },
    };
</script>

<style lang="scss">
    @import '../assets/variables.scss';

    nav {
        transition: all 0.5s ease;
        font-family: 'Orbitron', sans-serif;
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        border: none;
        height: $navigation-height;
        display: flex;
        align-items: center;
        justify-content: space-between;
        z-index: 5;
        //filter: blur(2px);
        & ul {
            display: flex;
            flex-direction: row;
            //margin-right: 1em;
            list-style-type: none;
            margin: 0;
            padding-left: 0;
        }
        & li {
            margin-right: 1em;
        }
        & a {
            text-decoration: none;
            color: white;
            transition: all .25s linear;
        }
    }


    $colors: (
        one: $red,
        two: $blue,
        three: $yellow,
        four: $purple,
    );

    @each $section, $color in $colors {
        .#{$section}.active {
            color: $color;
            border-bottom: 3.5px solid $color;
        }
        .#{$section}:hover {
            //color: $color;
            border-bottom: 3.5px solid $color;
        }
    }   


    @media only screen and (max-width: 600px) {
        nav {
            & li {
                font-size: 0.8em;
            }
        }
    }

</style>