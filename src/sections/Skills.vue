<template>
    <div id="skills">
        <h2>Mes compétences</h2>
        <div class="skills">
            <div class="skill">
                <h3>Dévelopement Front End</h3>
                <ul>
                    <li>JavaScript/TypeScript</li>
                    <li>Angular/Vue.js/React.js</li>
                    <li>Jest/Cypress</li>
                </ul>
            </div>
            <div class="skill">
                <h3>Dévelopement Back End</h3>
                <ul>
                    <li>Node.js (Express)</li>
                    <li>PHP (Symfony, Laravel)</li>
                    <li>SQL (Oracle, PostgreSQL, MySQL)</li>
                </ul>
            </div>
            <div class="skill">
                <h3>Autres</h3>
                <ul>
                    <li>Versioning et intégration continue avec git/svn et Jenkins/CircleCI</li>
                    <li>Gestion de projets, méthodes agiles, SCRUM, management</li>
                    <li>Utilisation d'outil de design comme Sketch, Figma ou Photoshop</li>
                </ul>
            </div>
        </div>
    </div>
</template>

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