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

    </section>
</template>

<style scoped>
    
#project-category{
    padding: 0 10%;
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

</style>