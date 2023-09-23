<template>
    <nav id="nav">
        <nuxt-link to="/" class="logo"><img src="~/assets/img/logo.png" alt="My Logo"/></nuxt-link>
        <ul class="nav-menu" :class="{ active: isMobileMenuOpen }">
            <li class="second-child"><nuxt-link to="/">Home</nuxt-link></li>
            <li><nuxt-link to="/project">Projects</nuxt-link></li>
            <li><nuxt-link to="/article">Articles</nuxt-link></li>
            <li><nuxt-link to="https://docs.google.com/document/d/11IuNP9FyhCVXl6XM002H7dBl5NrFMz1i3Lvjmccxt8M/edit">CV</nuxt-link></li>
            <li><nuxt-link to="https://lucky-torrone-b3f911.netlify.app/">Games</nuxt-link></li>
        </ul>
        <div class="nav-right">
            <div>
                <label class="switch">
                <input type="checkbox">
                <span class="slider round"></span>
                </label>
            </div>
            <div class="hamburger" :class="{ active: isMobileMenuOpen }" @click="toggleMobileMenu">
                <span class="bar"></span>
                <span class="bar"></span>
                <span class="bar"></span>
            </div>
        </div>
    </nav>
</template>

<script>
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
    setup() {
        
    },
    data() {
        return {
        isMobileMenuOpen: false,
        };
    },
    methods: {
        toggleMobileMenu() {
            this.isMobileMenuOpen = !this.isMobileMenuOpen;
        },
    },
})
</script>
  
<style scoped>
    nav {
        color: #fff;
        padding: 0 5% 0 5%;
        align-items: center;
        min-height: 100px;
        display: flex;
    }

    .nav-menu {
        list-style: none;
        display: flex;
        align-items: center;
        gap: 40px;
    }

    .nav-right{
        display:flex;
        margin-left:auto;
        gap: 40px;
    }

    /* li:last-child{
        margin-left:auto;
    } */

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

    .hamburger{
        display:none;
    }

    .bar{
        display: block;
        width: 25px;
        height: 3px;
        margin: 5px auto;
        -webkit-transition: all 0.3s ease-in-out;
        transition: all 0.3s ease-in-out;
        background-color: white;
    }

    @media only screen and (max-width: 768px) {
        .hamburger {
            display: block;
            cursor: pointer;
        }

        .hamburger.active .bar:nth-child(2){
            opacity:0;
        }

        .hamburger.active .bar:nth-child(1){
            transform: translateY(8px) rotate(45deg);
        }

        .hamburger.active .bar:nth-child(3){
            transform: translateY(-8px) rotate(-45deg);
        }
        
        /* nav{
            justify-content: space-between;
        } */

        .nav-menu{
            position: fixed;
            left: -100%;
            top: 70px;
            gap: 0;
            flex-direction: column;
            background-color: black;
            width: 100%;
            text-align:center;
            transition: 0.3s;
        }

        .nav-menu > li{
            margin: 16px 0;
        }

        .nav-menu.active{
            left:0;
        }
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

    .slider.round {
        border-radius: 34px;
    }

    .slider.round:before {
        border-radius: 50%;
    }

</style>