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

    </section>
</template>

<style scoped>
    
#artikel-category{
    padding: 0 10%;
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
}

.artikel-button a{
    text-decoration: none;
    color: black;
}

</style>