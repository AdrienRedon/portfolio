<template>
    <portfolio-section class="wrapper">
        <h2>Qui suis-je ?</h2>
        <div class="container">
            <div class="flex">
                <h3>Adrien Redon, {{ age }} ans</h3>
                <h3>Développeur Web</h3>
                <p>Bonjour, je suis originaire de la région lyonnaise et diplomé Ingénieur en informatique à l'école CPE Lyon. Après une expérience de 3 ans en tant que développeur web au sein de la DSI d'Orange, je suis aujourd'hui Lead tech front à Geolid.</p>
                <p>Passionné par les nouvelles technologies, je prends plaisir à me tenir à jour dans ma veille. Smart Home, VR / AR, AI sont des sujets sur lesquels je garde un oeil.</p>
                <p>J'aime aussi voyager et je pratique de nombreux sports (escalade, triathlon, snowboard, yoga, etc...)</p>
                <p>Ce portfolio a pour but de présenter certaines de mes réalisations. Vous pouvez également visualiser mon CV et le télécharger.</p>
            </div>
            <div>
                <div class="picture"> 
                    <img src="/assets/img/snowboard.png">
                </div>
            </div>
        </div>
        <a href="/assets/AdrienREDON.pdf" class="btn">Télécharger</a>
        <skills id="skills"></skills>
    </portfolio-section>
</template>

<script>
    import moment from 'moment';
    import PortfolioSection from '../components/PortfolioSection.vue';
    import Skills from './Skills.vue';

    export default {
        components: {
            PortfolioSection,
            Skills,
        },
        computed: {
            age () {
                return moment().diff('1996-03-21', 'years');
            }
        }
    }
</script>

<style scoped>
    .wrapper {
        display: -webkit-flex;
        display: -moz-flex;
        display: -ms-flex;
        display: -o-flex;
        display: flex;
        flex-direction: column;
    }
    .container {
        display: -webkit-flex;
        display: -moz-flex;
        display: -ms-flex;
        display: -o-flex;
        display: flex;
        padding: 0 20px;
        text-align: justify;
        flex-wrap: wrap;
        justify-content: space-around;
        align-items: center;
    }

    @media screen and (min-width: 700px) {
        .container > div {
            max-width: 60%;
        }
    }

    h3 {
    text-align: left;
    } 

    h3 {
        margin: 0;
    }

    .picture {
        height: 300px;
        width: 300px;
        border-radius: 50%;
        overflow: hidden;
    }

    .picture img {
        height: 300px;
        width: 300px;
    }

    #skills {
        flex: 1;
        margin-top: 50px;
        padding-bottom: 20px;
    }
    .btn {
        display: inline-block;
        margin: auto;
        height: 36px;
        line-height: 36px;
        vertical-align: middle;
        padding: 0 2rem;

        text-align: center;
        text-decoration: none;
        color: #fff;
        letter-spacing: .5px;
        
        background-color: #F05F40;
        border: none;
        border-radius: 2px;
        
        text-transform: uppercase;
        transition: .2s ease-out;
        cursor: pointer;
    }
</style>
