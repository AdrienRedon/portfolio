<template>
    <header>
        <h1>
            Adrien REDON – {{ age }} ans<br>
            Développeur Web et Mobile depuis {{ experience }} ans<br>
            Actuellement apprenti ingénieur
        </h1>
        <scroll-button href="#about" class="button"></scroll-button>
    </header>
</template>

<script>
    import moment from 'moment';
    import ScrollButton from './ScrollButton.vue';

    export default {
        components: {
            ScrollButton,
        },
        computed: {
            age () {
                return moment().diff('1996-03-21', 'years');
            }, 
            experience () {
                return moment().diff('2011-07-15', 'years');
            },
            poste () {
                if (moment().isBetween('2014-09-08', '2017-09-08')) {
                    return 'apprenti ingénieur';
                } else {
                    return 'ingénieur';
                }
            }
        }
    }
</script>

<style scoped>
    header {
        display: -webkit-flex;
        display: -moz-flex;
        display: -ms-flex;
        display: -o-flex;
        display: flex;
        -webkit-flex-direction: column;
        -moz-flex-direction: column;
        -ms-flex-direction: column;
        -o-flex-direction: column;
        flex-direction: column;
        background: url(/assets/img/header.jpg) center no-repeat;
        background-size: cover;
        height: 100vh;
    }

    h1 {
        text-transform: uppercase;
        margin: auto;
        text-align: center;
        color: white;
        font-size: 24px;
    }

    @media screen and (min-width: 700px) {
        h1 {
            font-size: 32px;
        }
    }

    .button {
        margin: 0 auto;
    }
</style>