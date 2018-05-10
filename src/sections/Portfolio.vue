<template>
    <portfolio-section>
        <h2>Portfolio</h2>
        <div class="works">
            <work v-for="work in works" :work="work" :key="work.id"></work>
        </div>
    </portfolio-section>
</template>

<script>
    import PortfolioSection from '../components/PortfolioSection.vue';
    import Work from '../components/Work.vue';

    export default {
        components: {
            PortfolioSection,
            Work,
        },
        data () {
            return {
                works: [
                    {
                        id: 0,
                        img: 'cpe-calendar.png',
                        description: 'Développement d\'un outil de gestion de calendriers pour les administratifs de l\'école CPE Lyon', 
                        technologies: 'Java, MySQL, Hibernate'
                    },
                    {
                        id: 1,
                        img: 'ludofactory.png',
                        description: 'Développement de modules pour l\'outil de gestion de projet et intégration de maquettes Photoshop', 
                        technologies: 'Redmine, Ruby, Ruby on Rails, SASS'
                    },
                    {
                        id: 2,
                        img: 'relaxapic.png',
                        description: 'Développement d\'un site web pour les professionnels d\'acupuncture', 
                        technologies: 'PHP, MySQL, Javascript, jQuery'
                    },
                    {
                        id: 3,
                        img: 'steadytrip.png',
                        description: 'Développement d\'une application pour l\'organisation de voyages entre amis', 
                        technologies: 'C#, NodeJS, VueJS, SQL Server, Firebase Cloud Messaging'
                    },
                    {
                        id: 4,
                        img: 'thelatest.png',
                        description: 'Maintenance et évolution d\'un site web d\'agrégation d\'actualités et développement d\'une application mobile hybride', 
                        technologies: 'PHP, Symfony 2, Angular, Ionic 2'
                    },
                    {
                        id: 5,
                        img: 'uml-generator.png',
                        description: 'Développement d\'un outil pour réaliser des diagrammes MCD', 
                        technologies: 'VueJS, jQuery'
                    },
                    {
                        id: 6,
                        img: 'matchpoint.png',
                        description: 'Développement d\'une application mobile pour la gestion de club sportif lors d\'un hackathon de 24h', 
                        technologies: 'React Native, NodeJS, Hapi, PostgreSQL'
                    },
                    {
                        id: 7,
                        img: 'vue-me.png',
                        description: 'Développement d\'un assistant personnel avec reconnaissance vocale et analyse contextuelle lors d\'un hackathon de 24h', 
                        technologies: 'VueJS, api.ai, Speech Recognition, Speech Synthesis'
                    },
                    {
                        id: 8,
                        img: 'aerosmith.jpeg',
                        description: 'Développement du backend tournant sur un Raspberry Pi servant à piloter un drône transformé en hovercraft',
                        technologies: 'NodeJS, ExpressJS, WebSocket'
                    }
                ]
            }
        }
    }
</script>

<style scoped>
    .works {
        display: -webkit-flex;
        display: -moz-flex;
        display: -ms-flex;
        display: -o-flex;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
    }
    
</style>
