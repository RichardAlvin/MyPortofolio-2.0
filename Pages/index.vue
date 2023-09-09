<template>
    <main class="home-page">
        <section id="hero">
            <div class="hero-left">
                <h1><span style="color:#0dd354">Richard</span> Alvin Pratama,<br>Software Engineer</h1>
                <div class="hero-left-button">
                    <a href="#skills">Skills</a>
                    <a href="#faq">FaQ</a>
                </div>
                <div class="hero-left-experience">
                    <div>
                        <h1>1.5+</h1>
                        <p>Year of<br>Career Experience</p>
                    </div>
                    <div>
                        <h1>9+</h1>
                        <p>Contributed<br>Corporated Projects</p>
                    </div>
                    <div>
                        <h1>5+</h1>
                        <p>Personal &<br>Team Projects</p>
                    </div>
                </div>
            </div>
            <div class="hero-right">
                <div class="hero-right-icon">
                    <div>
                        <a href="https://www.linkedin.com/in/richard-alvin-pratama-b03a27214/">
                            <svg xmlns="http://www.w3.org/2000/svg" width="55" height="55" fill="currentColor" class="bi bi-linkedin" viewBox="0 0 16 16">
                                <path d="M0 1.146C0 .513.526 0 1.175 0h13.65C15.474 0 16 .513 16 1.146v13.708c0 .633-.526 1.146-1.175 1.146H1.175C.526 16 0 15.487 0 14.854V1.146zm4.943 12.248V6.169H2.542v7.225h2.401zm-1.2-8.212c.837 0 1.358-.554 1.358-1.248-.015-.709-.52-1.248-1.342-1.248-.822 0-1.359.54-1.359 1.248 0 .694.521 1.248 1.327 1.248h.016zm4.908 8.212V9.359c0-.216.016-.432.08-.586.173-.431.568-.878 1.232-.878.869 0 1.216.662 1.216 1.634v3.865h2.401V9.25c0-2.22-1.184-3.252-2.764-3.252-1.274 0-1.845.7-2.165 1.193v.025h-.016a5.54 5.54 0 0 1 .016-.025V6.169h-2.4c.03.678 0 7.225 0 7.225h2.4z"/>
                            </svg>
                        </a>
                    </div>
                    <div>
                        <a href="https://github.com/RichardAlvin">
                            <svg xmlns="http://www.w3.org/2000/svg" width="55" height="55" fill="currentColor" class="bi bi-github" viewBox="0 0 16 16">
                                <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.012 8.012 0 0 0 16 8c0-4.42-3.58-8-8-8z"/>
                            </svg>
                        </a>
                    </div>
                    <div>
                        <a href="https://gitlab.com/richardalvinpratama">
                            <svg xmlns="http://www.w3.org/2000/svg" width="55" height="55" fill="currentColor" class="bi bi-git" viewBox="0 0 16 16">
                                <path d="M15.698 7.287 8.712.302a1.03 1.03 0 0 0-1.457 0l-1.45 1.45 1.84 1.84a1.223 1.223 0 0 1 1.55 1.56l1.773 1.774a1.224 1.224 0 0 1 1.267 2.025 1.226 1.226 0 0 1-2.002-1.334L8.58 5.963v4.353a1.226 1.226 0 1 1-1.008-.036V5.887a1.226 1.226 0 0 1-.666-1.608L5.093 2.465l-4.79 4.79a1.03 1.03 0 0 0 0 1.457l6.986 6.986a1.03 1.03 0 0 0 1.457 0l6.953-6.953a1.031 1.031 0 0 0 0-1.457"/>
                            </svg>
                        </a>
                    </div>
                </div>
            </div>
        </section>
        <section id="info">
            <div class="info-container">
                <div class="div1">About</div>
                <div class="div2">Project</div>
                <div class="div3">Logo</div>
                <div class="div4">Article</div>
                <div class="div5">Connect</div>
            </div>
        </section>
        <section id="skills">
            <h1>My Skills</h1>
            <div class="skill-collection">
                <div v-for="skill in skillList" :key="skill.name" :class="getSkillClassName(skill.name)">
                    <div class="skill-hover" >
                        <p>Status: {{ skill.status }}</p>
                        <p>Experience: {{ skill.experience }}</p>
                        <p>Projects: {{ skill.projects }}</p>
                    </div>
                </div>
            </div>
        </section>
        <section id="certifications">
            <h1>Certifications</h1>
        </section>
        <section id="faq">
            <h1>Frequently Ask Question</h1>
            <div class="faq-row">

            </div>
        </section>
    </main>
</template>

<script>
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
    setup() {
        
    },

    data(){
        return{
            skillList: [
                {name: "net", status: "Advanced", experience: "1.2 Years", projects: "3"},
                {name: "laravel", status: "Advanced", experience: "2.5 Years", projects: "3"},
                {name: "flask", status: "Intermediate", experience: "2 Years", projects: "3"},
                {name: "node", status: "Intermediate", experience: "2.5 Years", projects: "3"},
                {name: "sqlserver", status: "Advanced", experience: "1.2 Years", projects: "3"},
                {name: "mysql", status: "Advanced", experience: "3 Years", projects: "3"},
                {name: "nuxtjs", status: "Intermediate", experience: "0.5 Years", projects: "3"},
                {name: "redhat", status: "Intermediate", experience: "2 Years", projects: "3"},
                {name: "gcp", status: "Intermediate", experience: "1.5 Years", projects: "3"},
                {name: "alibaba", status: "Intermediate", experience: "0.8 Years", projects: "3"},
                {name: "azure", status: "Basic", experience: "1 Years", projects: "3"},
                {name: "aws", status: "Basic", experience: "2 Years", projects: "3"},
                {name: "python", status: "Intermediate", experience: "3 Years", projects: "3"},
                {name: "arduino", status: "Intermediate", experience: "3 Years", projects: "3"},
                {name: "git", status: "Advanced", experience: "3.5 years", projects: "3"}
            ]
        }
    },

    methods:{
        getSkillClassName(name){
            return `skill-${name} skill-div`;
        }
    }
})
</script>


<style scoped>
#hero{
    height: 550px;
    overflow: hidden;
    width:100%;
    margin-top: 57px;
    display: flex;
}

.hero-left{
    max-width: 1140px;
    margin: 0 auto;
    flex: 0.9;
}

.hero-left h1{
    color: white;
    font-size: 75px;
    margin-top: 0px;
    margin-bottom: 40px;
}

.hero-left-button a{
    padding: 15px 20px;
    border-radius: 5%;
    margin-right: 5px;
    text-decoration: none;
    font-size: 24px;
}

.hero-left-button a:first-child{
    background-color: white;
    color: black;
}

.hero-left-button a:last-child{
    background-color: #0dd354;
    color: white;
}

.hero-left-experience{
    margin-top: 75px;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

.hero-left-experience h1{
    margin:0;
}

.hero-left-experience p{
    color: white;
    margin: 0px;
    font-size: 25px;
}

.hero-right{
    flex: 0.1;
    text-align: center;
}

.hero-right-icon div:not(:first-child){
    margin-top: 20px;
}

.hero-right-icon a{
    color:white;
}

#info{
    padding: 60px 5%;
}

.div1{ grid-area: about;}
.div2{ grid-area: project;}
.div3{ grid-area: logo;}
.div4{ grid-area: article;}
.div5{ grid-area: connect;}

.info-container{
    display:grid;
    grid-template-areas: 
    'about about about project project'
    'article article logo project project'
    'article article connect connect connect';
    gap: 5px;
    padding: 10px;
}

.info-container > div{
    background-color: white;
    padding: 40px 20px;
    font-size: 40px;
    color: white;
}

#skills{
    background-color:#242526;
    padding: 60px 10%;
}

#skills h1{
    text-align: center;
    color: white;
    font-size: 60px;
}

.skill-collection{
    display:grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 20px;
}

.skill-collection > div{
    background-color: black;
    background-size: cover;
    height: 200px;
    color: white;
    position: relative;
    background-position: center;
}


.skill-hover{
    position: absolute;
    top:0;
    left:0;
    width:100%;
    height: 100%;
    background-color: rgba(0,0,0, 1);
    opacity:0;
    transition: opacity 0.3s ease-in-out;
}

.skill-hover p{
    font-size: 24px;
    text-align: center;
}

.skill-div:hover .skill-hover{
    opacity: 0.8;
}

.skill-net{ background-image: url("~/assets/img/skill-icon/net.jpg") }
.skill-laravel{ background-image: url("~/assets/img/skill-icon/laravel.png")}
.skill-flask{ background-image: url("~/assets/img/skill-icon/flask.png")}
.skill-node{ background-image: url("~/assets/img/skill-icon/node.jpg")}
.skill-sqlserver{ background-image: url("~/assets/img/skill-icon/sqlserver.jpg")}
.skill-mysql{ background-image: url("~/assets/img/skill-icon/mysql.png")}
.skill-nuxtjs{ background-image: url("~/assets/img/skill-icon/nuxtjs.png")}
.skill-redhat{ background-image: url("~/assets/img/skill-icon/redhat.webp")}
.skill-gcp{ background-image: url("~/assets/img/skill-icon/gcp.png")}
.skill-aws{ background-image: url("~/assets/img/skill-icon/aws.jpg")}
.skill-azure{ background-image: url("~/assets/img/skill-icon/azure.webp")}
.skill-alibaba{ background-image: url("~/assets/img/skill-icon/alibaba.webp")}
.skill-arduino{ background-image: url("~/assets/img/skill-icon/arduino.jpg")}
.skill-python{ background-image: url("~/assets/img/skill-icon/python.webp")}
.skill-git{ background-image: url("~/assets/img/skill-icon/git.png")}


#certifications{
    height:300px;
}

#certifications h1{
    text-align: center;
    color: white;
}

#faq{
    background-color:#242526;
    height:300px; 
}

#faq h1{
    text-align: center;
    color: white;
}

</style>