<template>
    <nav id="nav">
      <ul>
        <li>
            <div class="logo">
                <img src="~/assets/img/logo.png" alt="My Logo"/>
            </div>
        </li>
        <li class="second-child"><a href="/">Home</a></li>
        <li><a href="/project">Projects</a></li>
        <li><a href="/article">Articles</a></li>
        <li><a href="https://docs.google.com/document/d/11IuNP9FyhCVXl6XM002H7dBl5NrFMz1i3Lvjmccxt8M/edit">CV</a></li>
      </ul>
    </nav>
</template>
  
<style scoped>
    nav {
    color: #fff;
    padding: 20px;
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
</style>