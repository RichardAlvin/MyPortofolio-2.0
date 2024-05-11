<template>
    <section id="project-category">
        <div class="project-button">
            <a @click="changeCategory('software-engineer')"><div>Software Engineer</div></a>
            <a @click="changeCategory('cloud-devops')"><div>Cloud & DevOps</div></a>
            <a @click="changeCategory('artificial-intelligence')"><div>Machine Learning</div></a>
            <a @click="changeCategory('embedded-iot')"><div>Embedded & IoT</div></a>
            <div style="background-color: grey;"></div>
            <a @click="changeCategory('others')"><div>Others</div></a>
        </div>
    </section>
    <section id="project">
        <div class="project-list">
            <div v-for="project in projects.data" class="project-card">
                <div class="project-img">
                    <!-- <img src="~/assets/img/skill-icon/net.jpg" /> -->
                </div>
                <div class="project-content">
                    <h3>{{ project.title }}</h3>
                    <p>{{ formatDateTime(project.created_at) }}</p>
                    <p>{{ project.body }}</p>
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

<script setup>
const categorySlug = ref(null);
const apiUrl = computed(() => `http://127.0.0.1:8000/api/project?projectCategory=${categorySlug.value}`);

const { data: projects} = await useFetch(apiUrl);

const formatDateTime = (dateTimeString) => {
  const options = { year: 'numeric', month: 'long', day: 'numeric' };
  const formattedDate = new Date(dateTimeString).toLocaleDateString('en-GB', options);
  return formattedDate;
};

function changeCategory(slug){
    categorySlug.value = slug;
}
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