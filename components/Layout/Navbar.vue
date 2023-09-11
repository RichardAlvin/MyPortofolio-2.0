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
        <li><nuxt-link to="https://lucky-torrone-b3f911.netlify.app/">Games</nuxt-link></li>
        <li><label class="switch">
            <input type="checkbox">
            <span class="slider round"></span>
            </label>
        </li>
      </ul>
    </nav>
</template>
  
<style scoped>
    nav {
    color: #fff;
    padding: 20px;
    padding: 10px 5% 10px 5%;
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

    li:last-child{
        margin-left:auto;
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

    .switch {
        position: relative;
        display: inline-block;
        width: 60px;
        height: 34px;
    }

    .switch input { 
        opacity: 0;
        width: 0;
        height: 0;
    }

    .slider {
        position: absolute;
        cursor: pointer;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: #ccc;
        -webkit-transition: .4s;
        transition: .4s;
    }

    .slider:before {
        position: absolute;
        content: "";
        height: 26px;
        width: 26px;
        left: 4px;
        bottom: 4px;
        background-color: white;
        -webkit-transition: .4s;
        transition: .4s;
    }

    input:checked + .slider {
        background-color: #2196F3;
    }

    input:focus + .slider {
        box-shadow: 0 0 1px #2196F3;
    }

    input:checked + .slider:before {
        -webkit-transform: translateX(26px);
        -ms-transform: translateX(26px);
        transform: translateX(26px);
    }

    /* Rounded sliders */
    .slider.round {
        border-radius: 34px;
    }

    .slider.round:before {
        border-radius: 50%;
    }
</style>