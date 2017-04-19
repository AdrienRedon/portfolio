<template>
    <nav class="menu menu--titania">

        <div class="title" id="title" @click="scrollTop">        
            <h1>Adrien Redon</h1>
        </div>

        <ul class="menu__list">
            <li class="menu__item"><a href="#about" class="menu__link">A propos</a></li>
            <li class="menu__item"><a href="#portfolio" class="menu__link">Portfolio</a></li>
            <li class="menu__item"><a href="#contact" class="menu__link">Contact</a></li>
            <li class="menu__lines"></li>
        </ul>

    </nav>
</template>

<script>
    import jquery from 'jquery';
    import onePageNav from '../utils/jquery.nav';

    export default {
        mounted () {
            const deviceWidth = document.querySelector('html').offsetWidth;
            jquery('.menu__list').onePageNav({
                currentClass: 'menu__item--current',
                offset: (deviceWidth < 700) ? 0 : 60,
                begin: function() {
                    //Hack so you can click other menu items after the initial click
                    jquery('body').append('<div id="device-dummy" style="height: 1px;"></div>');
                },
                end: function() {
                    jquery('#device-dummy').remove();
                }
            });
        },
        methods: {
            scrollTop (event) {
                event.preventDefault();
                jquery('html, body').animate({
                    scrollTop: 0
                }, 750);
            }
        }
    }
</script>

<style scoped>
    a {
        text-decoration: none;
    }

    .menu {
        display: -webkit-flex;
        display: -moz-flex;
        display: -ms-flex;
        display: -o-flex;
        display: flex;
        justify-content: space-between;
        line-height: 1;
        padding: 5px;

        background-color: #2a282b;
    }

    .menu .title {
        display: none;
        margin-left: 10px;
    }

    @media screen and (min-width: 700px) {
        .menu .title {
            display: block;
        }
    }

    .menu .title h1 {
        cursor: pointer;
        font-size: 1.2rem;
        font-weight: bold;
        color: #EEE;
    }

    .menu__list {
        position: relative;
        display: -webkit-flex;
        display: -moz-flex;
        display: -ms-flex;
        display: -o-flex;
        display: flex;
        -webkit-flex-wrap: wrap;
        flex-wrap: nowrap;
        margin: 0;
        padding: 0;
        list-style: none;
    }

    .menu__item {
        display: block;
        margin: .5em 0;
    }

    .menu__link {
        font-size: 1em;
        font-weight: bold;
        display: flex;
        padding: 1em;
        justify-content: center;
        -webkit-flex-direction: column;
        -moz-flex-direction: column;
        -ms-flex-direction: column;
        -o-flex-direction: column;
        flex-direction: column;
        text-align: center;
        cursor: pointer;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
        -webkit-touch-callout: none;
        -khtml-user-select: none;
        -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
    }

    .menu__link:hover,
    .menu__link:focus {
        outline: none;
    }

    /* Titania (by @rileyjshaw) */
    .menu--titania .menu__item {
        margin: 0;
    }

    .menu--titania .menu__link {
        width: 110px;
        height: 3em;
        text-align: center;
        color: #b5b5b5;
        -webkit-transition: color 0.3s 0.2s;
        transition: color 0.3s 0.2s;
    }

    .menu--titania .menu__link:hover,
    .menu--titania .menu__link:focus {
        color: #929292;
    }

    .menu--titania .menu__item--current .menu__link {
        color: #F05F40;
        -webkit-transition: color 0.7s 0.2s;
        transition: color 0.7s 0.2s;
    }

    .menu--titania .menu__lines {
        position: absolute;
        top: 0;
        left: 0;
        width: 110px;
        height: 100%;
        pointer-events: none;
        border: 2px solid #F05F40;
        border-width: 2px 0;
        -webkit-transition: -webkit-transform 0.5s 0.2s;
        transition: transform 0.5s 0.2s;
        -webkit-transition-timing-function: cubic-bezier(1, 0.01, 0, 1);
        -webkit-transition-timing-function: cubic-bezier(1, 0.01, 0, 1.22);
        transition-timing-function: cubic-bezier(1, 0.01, 0, 1.22);
    }

    /* vertical lines */
    .menu--titania .menu__lines::before,
    .menu--titania .menu__lines::after {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        border: 2px solid #F05F40;
        border-width: 0 2px;
        -webkit-transform-origin: 0% 50%;
        transform-origin: 0% 50%;
    }

    /* animates out at transition start */
    .menu--titania .menu__lines::before {
        -webkit-transform: scale3d(1, 0, 1);
        transform: scale3d(1, 0, 1);
        -webkit-transition: -webkit-transform 0.2s ease;
        transition: transform 0.2s ease;
    }

    /* animates back in at transition end */
    .menu--titania .menu__lines::after {
        -webkit-transform: scale3d(1, 1, 1);
        transform: scale3d(1, 1, 1);
        -webkit-transition: -webkit-transform 0.2s ease 0.7s;
        transition: transform 0.2s ease 0.7s;
    }

    .menu--titania .menu__item:active:not(.menu__item--current) ~ .menu__lines::before,
    .menu--titania .menu__item:active:not(.menu__item--current) ~ .menu__lines::after {
        -webkit-transition: -webkit-transform 0s;
        transition: transform 0s;
    }

    .menu--titania .menu__item:active:not(.menu__item--current) ~ .menu__lines::before {
        -webkit-transform: scale3d(1, 1, 1);
        transform: scale3d(1, 1, 1);
    }

    .menu--titania .menu__item:active:not(.menu__item--current) ~ .menu__lines::after {
        -webkit-transform: scale3d(1, 0, 1);
        transform: scale3d(1, 0, 1);
    }

    .menu--titania .menu__item:nth-child(1).menu__item--current ~ .menu__lines {
        -webkit-transform: translate3d(0, 0, 0);
        transform: translate3d(0, 0, 0);
    }

    .menu--titania .menu__item:nth-child(2).menu__item--current ~ .menu__lines {
        -webkit-transform: translate3d(100%, 0, 0);
        transform: translate3d(100%, 0, 0);
    }

    .menu--titania .menu__item:nth-child(3).menu__item--current ~ .menu__lines {
        -webkit-transform: translate3d(200%, 0, 0);
        transform: translate3d(200%, 0, 0);
    }

    .menu--titania .menu__item:nth-child(4).menu__item--current ~ .menu__lines {
        -webkit-transform: translate3d(300%, 0, 0);
        transform: translate3d(300%, 0, 0);
    }

    .menu--titania .menu__item:nth-child(5).menu__item--current ~ .menu__lines {
        -webkit-transform: translate3d(400%, 0, 0);
        transform: translate3d(400%, 0, 0);
    }

    @media screen and (max-width: 720px) {
        .menu {
            -webkit-flex-direction: column;
            -moz-flex-direction: column;
            -ms-flex-direction: column;
            -o-flex-direction: column;
            flex-direction: column;
        }

        .menu .title h1 {
            display: none;
        }

        .menu__link {
            font-size: 1rem;
        }
    }
</style>