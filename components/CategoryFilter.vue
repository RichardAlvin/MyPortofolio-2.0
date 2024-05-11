<template>
    <section id="artikel-category">
        <div class="artikel-button">
            <a @click="changeCategory('software-engineer')"><div>Software Engineer</div></a>
            <a @click="changeCategory('cloud-devops')"><div>Cloud & DevOps</div></a>
            <a @click="changeCategory('artificial-intelligence')"><div>Machine Learning</div></a>
            <a @click="changeCategory('embedded-iot')"><div>Embedded & IoT</div></a>
            <div style="background-color: grey;"></div>
            <a @click="changeCategory('others')"><div>Others</div></a>
        </div>
    </section>
</template>

<script>
function changeCategory(slug) {
  $emit('categoryChanged', slug); // Emit event when category changes
}
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
</style>