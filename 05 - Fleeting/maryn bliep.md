 2024 - 14 - 14 14:57

tags: [[code]] [[Bliep!]] [[School]]

progress: >>

# maryn bliep

```
  

<!DOCTYPE html>

<html>

<head>

<meta charset="utf-8">

<meta http-equiv="X-UA-Compatible" content="IE=edge">

<title>Bliep!</title>

<meta name="description" content="">

<meta name="viewport" content="width=device-width, initial-scale=1">

<link rel="stylesheet" href="user.css">

<link href="https://cdn.jsdelivr.net/npm/remixicon@4.2.0/fonts/remixicon.css" rel="stylesheet"/>

<style>

    /*maryn salemink april 2024*/

  

:root {

--main-color: #5352ed;

--lighter-color: #f7f7ff;

--dark-color: #2f3542;

}

  

* {

margin: 0;

padding: 0;

}

*, ::before,::after{

box-sizing: border-box;

}

html {

  

-webkit-tap-highlight-color: transparent;

}

  

body {

font-family: 'Poppins', sans-serif;

font-size: 14px;

font-weight: 400;

line-height: 1.8;

color: var(--dark-color);

}

  

a {

text-decoration: none;

color: inherit;

}

  

.nav-container{

max-width: 100%;

margin: 0;

pointer-events: auto;

}

  

nav{

position: fixed;

bottom: 0;

width: 100%;

background-color: var(--lighter-color);

left: 0;

padding: 0;

border-top-left-radius: 33px;

border-top-right-radius: 33px;

box-shadow: rgb(50, 50, 93 / 25%) 0 50px 100px -20px,

            rgb(0, 0, 0 / 30%) 0 30px 60px -30px;

overflow: hidden;

}

nav ul {

display: flex;

align-items: center;

justify-content: space-between;

list-style-type: none; /* Add this line */

}

  

nav :where(li,a){

position: relative;

}

nav ul li a{

display: flex;

align-items: center;

justify-content: center;

flex-direction: column-reverse;

padding: 0;

font-size: 1.5em;

line-height: 1.4;

width: 80px;

height: 80px;

-webkit-transition: all .3s ease-out;

transition: all .3s ease-out;

}

nav ul li a:hover{

color: var(--main-color);

transition: all .3s ease-in;

}

  

nav ul li a span{

font-size: 10px;

}

  

/* animation */

  

nav li.active::before {

left: -20px;

border-radius: 0 30px 30px 0;

}

nav li.active::after{

right: -20px;

border-radius: 0 0 0 30px;

}

nav li.active::before, nav li.active::after {

background-color: var(--lighter-color);

top: 1px;

}

nav li a::before, nav li a::after{

content: '';

position: absolute;

background-color: var(--main-color);

z-index: -1;

border-radius: 10px 10px 0 0;

-wekbkit-transform: translateY(15px);

transform: translateY(15px);

-webkit-transition: transform .5s, border-radius .3s;

transition: transform .3s, border-radius .3s;

}

nav li.active a::before, nav li.active a::after {

-webkit-transform: translateY(0);

transform: translateY(0);

}

nav li.active a::before{

top: 10px;

left: 10px;

width: calc(100% - 20px);

height: 100%;

border-radius: 30px 30px 0 0;

}

nav li.active a::after {

left: -10px;

bottom: 0;

width: 100px;

height: 40px;

}

nav li.active a {

color: var(--lighter-color);

}

  

nav li .label {

position: absolute;

top: 8px;

max-width: 25px;

height: 15px;

padding: 0 2px;

z-index: 1;

border-radius: 3px;

color: #ff6b91;

background-color: #ff6b9133;

right: 20px;

}

nav li.active .label{

color: var(--lighter-color);

background-color: #ff6b91;

}

  

/* page scroll */

  

section {

display: flex; /* Change display to flex */

flex-direction: row; /* Set flex direction to row for horizontal alignment */

overflow-x: auto; /* Enable horizontal scrolling */

width: 100%; /* Ensure full width */

}

  

section > div {

min-width: 100vw; /* Set minimum width of each div to full viewport width */

flex: 0 0 auto; /* Ensure each div keeps its own width */

height: 100vh; /* Set height to full viewport height */

display: flex;

align-items: center;

justify-content: center;

font-size: 2.5em;

color: var(--lighter-color);

text-transform: uppercase;

font-weight: 800;

}

  

section > div:nth-child(1) {

background-color: aquamarine;

}

section > div:nth-child(2) {

background-color: #badc58;

}

section > div:nth-child(3) {

background-color: rgb(0, 140, 255);

}

section > div:nth-child(4) {

background-color: rgb(104, 33, 197);

}

section > div:nth-child(5) {

background-color: rgb(218, 145, 10);

}

  

/* Media queries for smaller screens */

@media (max-width: 480px) {

    nav ul li a {

        width: 60px;

        height: 60px;

        font-size: 1.2em;

    }

    nav li .label {

        position: absolute;

        top: 4px;

        max-width: 25px;

        height: 15px;

        padding: 0 1px;

        z-index: 1;

        border-radius: 3px;

        color: #ff6b91;

        background-color: #ff6b9133;

        right: 16px;

    }

    nav li.active .label{

        color: var(--lighter-color);

        background-color: #ff6b91;

    }

    nav li a::before, nav li a::after {

        transform: translateY(10px); /* Adjust transform for smaller navbar */

    }

    nav li::before, nav li::after{

        content: '';

        position: absolute;

        top: 1px;

        height: 100%;

        width: 25px;

    }

    nav li.active a::before {

        top: 5px; /* Adjust top position */

        left: 5px; /* Adjust left position */

        right: 0.5px;

        width: calc(100% - 10px); /* Adjust width */

        height: 100%; /* Adjust height */

        border-radius: 25px; /* Adjust border-radius */

    }

    nav li.active a::after {

        left: -15px; /* Adjust left position */

        bottom: 0px; /* Adjust bottom position */

        width: 90px; /* Adjust width */

        height: 20px; /* Adjust height */

        border-radius: 30px 30px 0 0; /* Adjust border-radius */

    }

}

  

@media (max-width: 360px) {

nav ul li a {

    width: 60px;

    height: 55px;

    font-size: 1.em;

}

nav li .label {

    position: absolute;

    top: 4px;

    max-width: 25px;

    height: 10px;

    padding: 0 1px;

    z-index: 1;

    border-radius: 3px;

    color: #ff6b91;

    background-color: #ff6b9133;

    right: 10px;

}

nav li.active .label{

    color: var(--lighter-color);

    background-color: #ff6b91;

}  

  

}

  
  

</style>

</head>

<body>

<div id="page" class="site">

<div class="nav-container">

    <nav>

        <ul>

            <li><a href="#contact"><span>contact</span><i class="ri-pencil-line"></i></a></li>

            <li><a href="#absent"><span>absent</span><i class="ri-profile-line"></i></a></li>

            <li class="active"><a href="#home"><span>home</span><i class="ri-home-smile-line"></i></a></li>

            <li><a href="#profile">

                <span>profile</span>

                <i class="ri-user-3-line"></i>

                <span class="label profile">1</span>

            </a></li>

            <li><a href="#setting"><span>settings</span><i class="ri-settings-3-line"></i></a></li>

        </ul>

    </nav>

    <section>

        <div id="contact">

            <h2>contact</h2>

        </div>

        <div id="absent">

            <h2>absent</h2>

        </div>

        <div id="home">

            <h2>home</h2>

        </div>

        <div id="profile">

            <h2>profile</h2>

        </div>

        <div id="setting">

            <h2>setting</h2>

        </div>

    </section>

</div>

</div>

  

<script>

// JavaScript for toggling active class on navbar items

const trigger = document.querySelectorAll('nav li');

trigger.forEach((menu) => menu.addEventListener('click', toggle));

  

function toggle() {

    trigger.forEach((item) => {

        if (item !== this) {

            item.classList.remove('active');

        }

    });

  

    if (!this.classList.contains('active')) {

        this.classList.add('active');

    }

}

  
  

</script>

</body>

</html>
```
**Refrences**
--