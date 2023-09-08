<template>
    <nav id="nav">
      <ul>
        <li>
            <div class="logo">
                <img src="~/assets/img/logo.png" alt="My Logo"/>
            </div>
        </li>
        <li class="second-child"><nuxt-link to="/">Home</nuxt-link></li>
        <li><nuxt-link to="/project">Projects</nuxt-link></li>
        <li><nuxt-link to="/article">Articles</nuxt-link></li>
        <li><nuxt-link to="https://docs.google.com/document/d/11IuNP9FyhCVXl6XM002H7dBl5NrFMz1i3Lvjmccxt8M/edit">CV</nuxt-link></li>
      </ul>
    </nav>
</template>
  
<style scoped>
    nav {
    color: #fff;
    padding: 20px;
    padding: 20px 5% 20px 5%;
    }

    ul {
    list-style: none;
    padding: 0;
    display: flex;
    align-items: center;
    }

    li:not(:first-child) {
        margin-left: 40px;
    }

    li.second-child{
        margin-left:80px;
    }

    .logo img{
        width:150px;
    }

    a {
    text-decoration: none;
    color: #fff;
    font-size: 30px;
    }

    a.router-link-active{
        color:#0dd354;
    }
</style>