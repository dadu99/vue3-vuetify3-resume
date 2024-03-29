<template>
    <v-card color="#F9EBC7">
        <v-card-text class=" fluid fill-height">
            <ContentSection title="Who am I?">
                <li>
                    I'm an UI developer
                </li>
                <li>
                    I'm interested and skilled in different topics of Information Technology including programming, web
                    development, computer and network security
                </li>
                <li>
                    Enthusiast and ambitious person, who enjoys challenges, keen to learn new things and working with
                    best professional people
                </li>
            </ContentSection>

            <ContentSection v-if="experience" title="Experience">
                <v-layout v-for="(proud, index) in experience" :key="index" class="layout-education">
                    <v-flex class="period-section">
                        <div class="head-experience">
                            <strong v-if="proud.title">{{ proud.title }}</strong>
                            <strong>{{ proud.from }}-{{ proud.to }}</strong>
                        </div>

                        <div v-if="proud.company">
                            <b class="font-weight-thin">{{ proud.company }}</b>
                        </div>
                        <div v-if="proud.description">
                            <span>&#8226;</span> {{ proud.description }}
                        </div>
                    </v-flex>
                </v-layout>
            </ContentSection>

            <ContentSection v-if="educations" title="Education">
                <v-layout v-for="(education, i) in educations" :key="i" class="layout-education">
                    <v-flex class="period-section">
                        <div class="head-experience">
                               <strong v-if="education.title">{{ education.title }}</strong>
                        <strong>{{ education.from }}-{{ education.to }}</strong>
                        </div>
                     
                        <div v-if="education.location">
                            <b class="font-weight-thin">{{ education.location }}</b>
                        </div>
                        <div v-if="education.description">
                            <span>&#8226;</span> {{ education.description }}   
                        </div>
                    </v-flex>
                </v-layout>
            </ContentSection>

            <ContentSection v-if="skills" id="to-timeline" title="Technical Skills">
                <div>
                    <div v-for="(skill, iterateSkill) in skills" :key="iterateSkill">
                        <v-flex v-if="skill.divider" md12 xs12 mb-4/>
                        <div class="mr-2 ml-2">
                            <div class="align-center">
                                <v-icon small>{{ skill.icon }}</v-icon>
                                {{ skill.title }}
                            </div>
                            <v-progress-linear class="progress"
                                               bg-color="blue-grey"
                                               color="black"
                                               height="3"
                                               :model-value="skill.value"/>
                        </div>
                    </div>
                </div>
            </ContentSection>

            <ContentSection v-if="personalProjects" title="Other technical skills">
                <v-layout class="layout-education">
                    <ul class="others-technical-skills">
                        <li> <span>&#8226;</span> Programming in Borland C++, MinGW Developer Studio, Microsoft Visual Studio, NetBeans,
                            Eclipse, IntelliJ IDEA;
                        </li>
                        <li>  <span>&#8226;</span> Knowledge in WordPress</li>
                        <li>  <span>&#8226;</span> Knowledge of ANSI c/C++, Java 11, OOP, Python, MS Office: Word, Power Point, Excel, Access</li>
                        <li>  <span>&#8226;</span> Basic knowledge in assembling language</li>
                        <li>  <span>&#8226;</span> Basic knowledge Windows Server</li>
                        <li>  <span>&#8226;</span> Software documentation development (technical and user guides)</li>
                        <li>  <span>&#8226;</span> Artificial Intelligence</li>
                    </ul>
                </v-layout>
            </ContentSection>

            <ContentSection v-if="personalProjects" title="Personal Projects">
                <v-layout v-for="(proj, indexProj) in personalProjects" :key="indexProj" class="layout-education">
                    <v-flex md8>
                        <div v-if="proj.projectDescription">
                            <li>{{ proj.projectDescription }}</li>
                        </div>
                    </v-flex>
                </v-layout>
            </ContentSection>
        </v-card-text>
    </v-card>
</template>

<script>
import ContentSection from "../AboutMe/ContentSection.vue";

export default {
    name: "AboutMe",

    components: {ContentSection},

    data() {
        return {
            educations: [
                {
                    from: '10/2020',
                    to: '07/2022',
                    title: 'Master\'s degree, Advanced Computing Systems',
                    location: '"Lucian Blaga" University of Sibiu',
                    description: 'Activities: Advanced Methods in Text Mining, Data Compression, Research Methods in Advanced Computing Architectures, Advanced Computer Graphics',
                },
                {
                    from: '10/2016',
                    to: '07/2020',
                    title: 'Bachelor\'s degree, Computer Science',
                    location: '"Lucian Blaga" University of Sibiu',
                    description: 'Activities: Computer Programming, Object-Oriented Programming, Web Development, Artificial Intelligence, Technologies for Application Development',
                },
                {
                    from: '09/2012',
                    to: '08/2016',
                    title: 'Bacalaureat Diploma',
                    location: '"Gheorghe Lazar" National College Sibiu',
                    description: '',
                },
            ],
            experience: [
                {
                    from: '03/2021',
                    to: 'Present',
                    title: 'Frontend Developer',
                    company: 'Scriptics Decisions, Sibiu',
                    description: 'Full-time: This is my first job after finishing the university. At this job I have a position of Frontend Developer but now I’m working as a full stack with frameworks PHP Laravel and Vue.js',
                },
                {
                    from: '11/2020',
                    to: '03/2021',
                    title: 'Frontend Developer',
                    company: 'Scriptics Decisions, Sibiu',
                    description: 'Part-time',
                },
                {
                    from: '07/2019',
                    to: '08/2019',
                    title: 'Backend Developer',
                    company: 'iQuest Group, Sibiu',
                    description: 'Project Name: Educational Application, Project Description: An education application for children from schools, where every child can read books from different subjects. I  was involved in creating the PostgreSQL database, managing it and solving tasks such as creating controllers for many categories, store/search documents, CRUD operations. Technologies used: Java 11, Maven, PostgreSQL, SpringBoot, Apache Solr',
                },
                {
                    from: '08/2018',
                    to: '07/2018',
                    title: 'Stundent Intern',
                    company: 'Ausy Technologies Sibiu',
                    description: 'Project Name: Slither.io game, Project Description: The game is played in matches between two players which integrate server-client side (working on it during summer practice). Technologies used: C++',
                },
            ],
            skills: [
                {
                    title: 'JavaScript',
                    icon: 'mdi-language-javascript',
                    value: 85,
                },
                {
                    title: 'PHP',
                    icon: 'mdi-language-php',
                    value: 80,
                },
                {
                    title: 'Laravel 8 Framework',
                    icon: 'mdi-laravel',
                    value: 75,
                },
                {
                    title: 'Vue.js Framework',
                    icon: 'mdi-vuejs',
                    value: 90,
                },
                {
                    title: 'PrimeVue',
                    icon: 'mdi-vuejs',
                    value: 85,
                },
                {
                    title: 'Pinia',
                    icon: 'mdi-vuejs',
                    value: 80,
                },
                {
                    title: 'Vite.js',
                    icon: 'mdi-vuejs',
                    value: 80,
                },
                {
                    title: 'Vuetify',
                    icon: 'mdi-vuetify',
                    value: 70,
                },
                {
                    title: 'WordPress',
                    icon: 'mdi-wordpress',
                    value: 90,
                },
                {
                    title: 'HTML',
                    icon: 'mdi-language-html5',
                    value: 90,
                },
                {
                    title: 'CSS, SCSS',
                    icon: 'mdi-language-css3',
                    value: 90,
                },
                {
                    title: 'Git',
                    icon: 'mdi-git',
                    value: 90,
                },
                {
                    title: 'Trello',
                    icon: 'mdi-trello',
                    value: 90,
                },
                {
                    title: 'MySQL',
                    icon: 'mdi-database',
                    value: 40,
                },
                {
                    title: 'Linux Commands',
                    icon: 'mdi-linux',
                    value: 60,
                },
                {
                    title: 'Docker',
                    icon: 'mdi-docker',
                    value: 30,
                },
                {
                    title: 'Hardware Development',
                    icon: 'mdi-chip',
                    value: 60,
                },
                {
                    title: 'C/C++',
                    icon: 'mdi-language-cpp',
                    value: 90,
                },
                {
                    title: 'Leadership',
                    icon: 'mdi-account-group',
                    value: 96,
                },
            ],
            personalProjects: [
                {
                    project: '1',
                    projectDescription: 'Project for achieving master degree: Python application: Medical Image Segmentation using Deep Learning Methods The goals of this application was to compare different neural networks architectures in order to segment the CT images',
                },
                {
                    project: '2',
                    projectDescription: 'C# application that simulating a microarchitecture of a computer system',
                },
                {
                    project: '3',
                    projectDescription: 'Project for achieving bachelor degree: C# application: Comparison k-Means algorithms in clustering techniques. This project means to develop different algorithms and evaluate them',
                },
                {
                    project: '4',
                    projectDescription: 'Network rock-paper-scissors game, between two players, developed in Borland C++ Builder 6. 4 Notions of OOP and image manipulation have been used.'
                },
                {
                    project: '5',
                    projectDescription: 'Web application online car auctions using PHP and MySQL language'
                },
                {
                    project: '6',
                    projectDescription: 'User administration to manage all users from admin panel in laravel 8 and bootstrap. This application is designed to manage all users as an admin. A user is of 3 types, it can be editor, author or admin. An admin has full roles, can create new users, edit and delete users. Also, the administrator can check the mail of a user or send him a notification to check the mail. For now, a user can only see his profile'
                },
                {
                    project: '7',
                    projectDescription: 'Created a page that serves as a curriculum vitae in Vue3 and Vuetify3, the one you are already on now :)'
                }

            ],
        }
    },

    setup() {
        return {};
    },
}
</script>

<style scoped lang="scss">
.period-section {
  width: 90%;

  .head-experience {
    display: flex;
    justify-content: space-between;
    margin-top: 10px;
    color:black;
  }
}

.progress {
  margin-top: 0.1rem;
}

.layout-education {
  gap: 15px;
  line-height: 30px;
}
@media screen and (max-width: 550px) {
    .head-experience {
        gap: 99px;
        font-style: italic;
        text-align: left;
  }
}
</style>