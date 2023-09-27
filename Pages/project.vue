<template>
    <section id="project-category">
        <div class="project-button">
            <a href=""><div>Software Engineer</div></a>
            <a href=""><div>Cloud & DevOps</div></a>
            <a href=""><div>Machine Learning</div></a>
            <a href=""><div>Embedded & IoT</div></a>
            <div style="background-color: grey;"></div>
            <a href=""><div>Others</div></a>
        </div>
    </section>
    <section id="project">
        <div class="project-list">
            <div v-for="project in projectList" :key="project.title" class="project-card">
                <div class="project-img">
                    <img src="~/assets/img/skill-icon/net.jpg" />
                </div>
                <div class="project-content">
                    <h3>{{ project.title }}</h3>
                    <p>{{ project.created_at }}</p>
                    <p>test test test test eorh goieh gioerg hoerhgoiergi eriogieor goi ergoier gero goierh ogie hriogherio goier hgoi erhhigo erogoeri gio oigeroigh geroigheor</p>
                </div>
                <div class="project-card-hover">
                    <p>><br>READ MORE</p>
                </div>
            </div>
        </div>
        <div class="btn-load-more">
            <button>LOAD MORE</button>
        </div>
    </section>
</template>

<script>
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
    setup() {
        
    },

    data(){
        return{
            projectList: [
                {title: "net", created_at: "12 September 2023", img: "assets/img/skill-icon/net.jpg", slug: "3"},
                {title: "test", created_at: "13 September 2023", img: "/assets/img/skill-icon/net.jpg", slug: "3"},
                {title: "fer", created_at: "14 September 2023", img: "/assets/img/skill-icon/net.jpg", slug: "3"},
                {title: "net", created_at: "15 September 2023", img: "/assets/img/skill-icon/net.jpg", slug: "3"},
                {title: "ghe", created_at: "2 September 2023", img: "/assets/img/skill-icon/net.jpg", slug: "3"},
                {title: "net", created_at: "1 September 2023", img: "/assets/img/skill-icon/net.jpg", slug: "3"},
            ]
        }
    }
})
</script>

<style scoped>
    
#project-category{
    padding: 2% 10% 0 10%;
    background-color: #242526;
}

.project-button{
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    padding: 10px;
    gap: 5px;
}

.project-button div{
    background-color: white;
    padding: 10px 0 10px 0;
    text-align: center;
}

.project-button a{
    text-decoration: none;
    color: black;
}

.project-button div:hover {
    background-color: #0dd354;
}

#project {
    padding: 2% 15%;
    background-color: #242526;
}

.project-list{
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
}

.project-card {
    width: calc(50% - 20px);
    background-color: white;
    color: black;
    box-sizing: border-box;
    position: relative;
    overflow: hidden;
    display:flex;
}

.project-img{
    flex:40%;
}

.project-img img{
    max-width: 100%;
    height: auto;
}

.project-content{
    flex: 60%;
    padding: 5px 10px;
}

.project-content p{
    margin: 0;
    padding: 5px 0;
}

.project-content h3{
    margin-top: 5px;
    margin-bottom: 0px;
}

.project-card-hover {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(13, 211, 82, 0.6);
    display: none;
    justify-content: center;
    align-items: center;
    text-align: center;
    color: white;
}

.project-card:hover .project-card-hover {
    display: flex;
}

.btn-load-more{
    display: flex;
    justify-content: center;
    margin: 30px 0px 0px 0px;
}

.btn-load-more button{
    background-color: white;
    padding: 10px 20px;
    color: black;
    transition: background-color 0.3s;
}

.btn-load-more button:hover{
    background-color: #0dd354;
}

@media only screen and (max-width: 768px) {
    .project-card {
        width: calc(100% - 20px);
        background-color: white;
        color: black;
        box-sizing: border-box;
        position: relative;
        overflow: hidden;
        display:flex;
    }
}

</style>