<template>
    <section id="artikel-category">
        <div class="artikel-button">
            <a href=""><div>Software Engineer</div></a>
            <a href=""><div>Cloud & DevOps</div></a>
            <a href=""><div>Machine Learning</div></a>
            <a href=""><div>Embedded & IoT</div></a>
            <div style="background-color: grey;"></div>
            <a href=""><div>Others</div></a>
        </div>
    </section>
    <section id="artikel">
        <div class="artikel-list">
            <div v-for="article in articleList" :key="article.title" class="artikel-card">
                <img src="~/assets/img/skill-icon/arduino.jpg" />
                <div class="artikel-content">
                    <p>{{ article.created_at }}</p>
                    <h3>{{ article.title }}</h3>
                </div>
                <div class="artikel-card-hover">
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
            articleList: [
                {title: "net", created_at: "12 September 2023", img: "~/assets/img/skill-icon/net.jpg", slug: "3"},
                {title: "test", created_at: "13 September 2023", img: "~/assets/img/skill-icon/net.jpg", slug: "3"},
                {title: "fer", created_at: "14 September 2023", img: "~/assets/img/skill-icon/net.jpg", slug: "3"},
                {title: "net", created_at: "15 September 2023", img: "~/assets/img/skill-icon/net.jpg", slug: "3"},
                {title: "ghe", created_at: "2 September 2023", img: "~/assets/img/skill-icon/net.jpg", slug: "3"},
                {title: "net", created_at: "1 September 2023", img: "~/assets/img/skill-icon/net.jpg", slug: "3"},
            ]
        }
    }
})
</script>

<style scoped>
    
#artikel-category{
    padding: 2% 10% 0 10%;
    background-color: #242526;
}

.artikel-button{
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    padding: 10px;
    gap: 5px;
}

.artikel-button div{
    background-color: white;
    padding: 10px 0 10px 0;
    text-align: center;
    transition: background-color 0.3s;
}

.artikel-button div:hover {
    background-color: #0dd354;
}

.artikel-button a{
    text-decoration: none;
    color: black;
}

#artikel {
    padding: 2% 15%;
    background-color: #242526;
}

.artikel-list{
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
}

.artikel-card {
    width: calc(25% - 20px);
    background-color: white;
    color: black;
    box-sizing: border-box;
    position: relative;
    overflow: hidden;
}

.artikel-card img{
    max-width: 100%;
    height: auto;
}

.artikel-content{
    padding: 5px 10px;
}

.artikel-content p{
    margin: 0;
}

.artikel-content h3{
    margin-top: 5px;
    margin-bottom: 0px;
}

.artikel-card-hover {
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

.artikel-card:hover .artikel-card-hover {
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
    .artikel-card {
        width: calc(50% - 20px);
        background-color: white;
        color: black;
        box-sizing: border-box;
        position: relative;
        overflow: hidden;
    }
}

</style>