<template>
    <section id="artikel-category">
        <div class="artikel-button">
            <a @click="fetchArticles('software-engineer')"><div>Software Engineer</div></a>
            <a href=""><div>Cloud & DevOps</div></a>
            <a href=""><div>Machine Learning</div></a>
            <a href=""><div>Embedded & IoT</div></a>
            <div style="background-color: grey;"></div>
            <a href=""><div>Others</div></a>
        </div>
    </section>
    <section id="artikel">
        <div class="artikel-list">
            <div v-for="article in articles" :key="article.title" class="artikel-card">
                <nuxt-link :to="`/article/${article.slug}`" style="text-decoration: none; color: inherit;">
                    <img :src="article.thumbnail_image" />
                    <div class="artikel-content">
                        <p>{{ formatDateTime(article.created_at) }}</p>
                        <h3>{{ article.title }}</h3>
                    </div>
                    <div class="artikel-card-hover">
                        <p>><br>READ MORE</p>
                    </div>
                </nuxt-link>
            </div>
        </div>
        <div class="btn-load-more">
            <button>LOAD MORE</button>
        </div>
        <!-- <nav aria-label="Pagination" v-if="metas.value && metas.value.last_page">
            <ul class="pagination">
                <li v-for="index in metas.value.last_page" :key="index">Item {{ index }}</li>
            </ul>
        </nav> -->
    </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { useRouter } from 'vue-router';

const router = useRouter();

const articles = ref([]);
const metas = ref([]);

const fetchData = async () => {
  const apiUrl = 'http://127.0.0.1:8000/api/article';

  try {
    const response = await fetch(apiUrl);
    const data = await response.json();

    articles.value = data.data;
    metas.value = data.meta;
  } catch (error) {
    console.error('Error fetching data:', error);
  }
};

const formatDateTime = (dateTimeString) => {
  const options = { year: 'numeric', month: 'long', day: 'numeric' };
  const formattedDate = new Date(dateTimeString).toLocaleDateString('en-GB', options);
  return formattedDate;
};

const fetchArticles = async (category) => {
  try {
    await router.push({ path: '/article', query: { articleCategory: category } });
  } catch (error) {
    console.error('Error fetching articles:', error);
  }
};

onMounted(() => {
  fetchData();
});
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