<template>
    <div id="skills">
        <h2>Mes compétences</h2>
        <div class="skills">
            <div class="skill">
                <h3>Dévelopement Web</h3>
                <ul>
                    <li>{{ php }} ans d'expérience en PHP (Laravel, Symfony)</li>
                    <li>{{ ruby }} ans avec Ruby (Ruby on Rails)</li>
                    <li>{{ node }} ans avec NodeJS (Express, Sails, Restify, Hapi)</li>
                </ul>
            </div>
            <div class="skill">
                <h3>Dévelopement Mobile</h3>
                <ul>
                    <li>Développement d'applications hybrides à l'aide d'Angular 2 et Ionic 2</li>
                    <li>Plusieurs projets cross-plateforme développés avec React Native</li>
                </ul>
            </div>
            <div class="skill">
                <h3>Autres</h3>
                <ul>
                    <li>Versioning et intégration continue avec git/svn et Jenkins</li>
                    <li>Utilisation d'outil de design comme Sketch ou Photoshop</li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    import moment from 'moment';

    export default {
        computed: {
            php () {
                return moment().diff('2011-07-15', 'years');
            },
            ruby () {
                return moment().diff('2014-03-30', 'years');
            },
            node () {
                return moment().diff('2015-10-20', 'years');
            },
        }
    }
</script>

<style scoped>
    #skills {
        background-color: #F05F40;
        color: #fff;
    }
    ul {
        list-style-type: none;
        margin: 0;
        padding: 0;
        text-align: center;
    }
    .skills {
        display: -webkit-flex;
        display: -moz-flex;
        display: -ms-flex;
        display: -o-flex;
        display: flex;
        flex-direction: column;
        flex-wrap: wrap;
        justify-content: space-around;
    }
    .skill {
        padding: 10px;
    }
    @media screen and (min-width: 700px) {
        .skills {
            flex-direction: row;
        }
        .skill {
            min-width: 360px;
        }
    }
</style>