<template>
    <portfolio-section>
        <h2>Portfolio</h2>
        <div class="works">
            <work v-for="work in works" :work="work"></work>
        </div>
    </portfolio-section>
</template>

<script>
    import PortfolioSection from './PortfolioSection.vue';
    import Work from './Work.vue';

    export default {
        components: {
            PortfolioSection,
            Work,
        },
        data () {
            return {
                works: [
                    {
                        img: 'cpe-calendar', 
                        description: 'Développement d\'un outil de gestion de calendriers pour les administratifs de l\'école CPE Lyon', 
                        technologies: 'Java, MySQL, Hibernate'
                    },
                    {
                        img: 'ludofactory', 
                        description: 'Développement de modules pour l\'outil de gestion de projet et intégration de maquettes Photoshop', 
                        technologies: 'Redmine, Ruby, Ruby on Rails, SASS'
                    },
                    {
                        img: 'relaxapic', 
                        description: 'Développement d\'un site web pour les professionnels d\'acupuncture', 
                        technologies: 'PHP, MySQL, Javascript'
                    },
                    {
                        img: 'steadytrip', 
                        description: 'Développement d\'une application pour l\'organisation de voyages entre amis', 
                        technologies: 'C#, NodeJS, VueJS, SQL Server, Firebase Cloud Messaging'
                    },
                    {
                        img: 'thelatest', 
                        description: 'Maintenance et évolution d\'un site web d\'agrégation d\'actualités et développement d\'une application mobile hybride', 
                        technologies: 'PHP, Symfony 2, Angular, Ionic 2'
                    },
                    {
                        img: 'uml-generator', 
                        description: 'Développement d\'un outil pour réaliser des diagrammes MCD', 
                        technologies: 'VueJS, jQuery'
                    },
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