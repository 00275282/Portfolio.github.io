<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE-edge">
        <meta name="viewport" content="width=device-width,initial-scale=1.0">
        <title>Portfolio website</title>
        <link rel="icon" href="{{ url_for('static', filename='favicon.ico') }}" type="image/x-icon">
        <link rel="stylesheet" href="{{ url_for('static', filename='css/p_main1.css') }}">
        <link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>
<style>
*{
    padding: 0;
    margin: 0;
    font-family: sans-serif;
    box-sizing: border-box;
    scroll-behavior: smooth;
    
}

:root{
    --bg-color: #051b29;
    --second-bg-color: #112e42;
    --text-color: #ededed;
    --main-color: #00abf0;
    --third-bg-color: #051b24;
    
}

body{
    
    background: var(--bg-color) ;
    color: var(--text-color);
}
.header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    color: var(--bg-color);
    padding: 20px 10%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 100%;
}

.logo {
    font-size: 25px;
    color: var(--text-color);
    text-decoration: none;
    font-weight: 600;
}

.logo:hover {
    color: #9370db;
}

.navbar {
    display: flex;
    justify-content: flex-start;
    align-items: center;
}

.navbar a {
    display: inline-block;
    font-size: 15px;
    color: var(--text-color);
    text-decoration: none;
    font-weight: 500;
    margin-left: 35px;
    transition: .3s;
}

.navbar a:hover {
    color: var(--main-color);
}


#menu-icon {
    color: var(--text-color);
    font-size: 3.6rem;
    cursor: pointer;
    display: none;
}


@media (max-width: 768px) {
    .navbar {
        display: none; 
        flex-direction: column;
        position: absolute;
        top: 70px;
        right: 0;
        background-color: var(--bg-color);
        width: 100%;
        padding: 20px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

   
    .navbar.active {
        display: flex;
    }

    .navbar a {
        margin-left: 0;
        margin-bottom: 15px; 
        font-size: 18px;
        text-align: center;
    }

    #menu-icon {
        display: block; 
    }

    .header {
        padding: 20px 5%; 
    }
}


section {
    min-height: 100vh;
    padding: 5rem 9% 2rem;
}

.home {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between; 
    padding: 0 10%;
    background: linear-gradient(rgba(0, 0, 255, 0.1), rgba(100, 200, 255, 0.1)), url('images/image2.jpeg');
    background-repeat: no-repeat;
    background-size: cover;
}

.home-content {
    max-width: 600px;
    display: flex;
    flex-direction: column;
    text-align: left; 
    column-gap: 0.5rem;
    margin-left: 5rem; 
}

.home-content h1 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
}

.home-content p {
    font-size: 1rem;
    margin-bottom: 2rem;
}

.home-content .btn {
    margin-left: 0;
    text-align: center;
}

.btn {
    display: flex;
    justify-content: center;
    width: 10rem;
    height: 3rem;
}

.btn .box {
    position: relative;
    display: inline-flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    background-color: var(--main-color);
    border: 0.2rem solid var(--main-color);
    border-radius: 0.8rem;
    color: var(--bg-color);
    z-index: 1;
    overflow: hidden;
}

.btn .box:hover {
    color: var(--main-color);
}

.btn .box::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 0%;
    height: 100%;
    background: var(--bg-color);
    z-index: -1;
    transition: 0.5s;
}

.btn .box:hover::before {
    width: 100%;
}

.home-sci {
    position: absolute;
    bottom: 4rem;
    width: 10rem;
    display: flex;
    justify-content: space-between;
}

.home-sci a {
    display: inline-flex;
    justify-content: center;
    align-items: center;
    width: 40px;
    height: 40px;
    background: transparent;
    border: 0.2rem solid var(--main-color);
    border-radius: 50%;
    font-size: 20px;
    color: var(--main-color);
    z-index: 1;
    position: relative;
    transition: 0.5s;
}

.home-sci a:hover {
    color: var(--main-color);
}

.home-sci a::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 0%;
    height: 100%;
    background: var(--second-bg-color);
    z-index: -1;
    border-radius: 100%;
    transition: 0.5s;
}

.home-sci a:hover::before {
    width: 100%;
}
@media (max-width: 768px) {
    .home {
        flex-direction: column;
        justify-content: center;
        padding: 3rem 5%;
    }

    .home-content {
        max-width: 100%;
        margin-left: 0; 
        text-align: center; 
    }

    .home-content h1 {
        font-size: 2rem; 
    }

    .home-content p {
        font-size: 0.9rem; 
    }

    .home-sci {
        bottom: 2rem; 
        width: 100%;
        justify-content: center;
    }

    .home-sci a {
        width: 35px;
        height: 35px;
        font-size: 18px;
    }
}

@media (min-width: 768px) and (max-width: 1024px) {
    .home {
        padding: 4rem 8%;
    }

    .home-content {
        max-width: 600px;
        text-align: center;
        margin-left: 3rem;
    }

    .home-sci {
        bottom: 3rem;
    }
}


.heading {
    font-size: 2rem;
    margin-bottom: 1rem;
    text-align: center;
}

span {
    color: var(--main-color);
}

.skills {
    min-height: 100vh;
    background-color: var(--bg-color);
}

.skills-list {
    display: flex;
    justify-content: space-between;
    gap: 20px;
    max-width: 900px;
    width: 100%;
    margin-left: 60px;
    padding-top: 30px;
    flex-wrap: wrap; 
}

.skill-box {
    background-color: transparent;
    border: 2px solid var(--main-color);
    padding: 20px;
    padding-bottom: 30px;
    width: 30%;
    text-align: center;
    border-radius: 10px;
    position: relative;
    z-index: 1;
    overflow: hidden;
    transition: .5s;
}

.titles {
    font-size: 24px;
    font-weight: bold;
    color: white;
}

.detail {
    position: absolute;
    padding: 10px;
    max-width: 100%;
    text-align: center;
    align-items: center;
    justify-content: space-around;
    font-size: 12px;
    font-weight: 100;
    color: white;
    transform: translate(-5%, -50%);
    opacity: 0;
    transition: opacity 0.3s ease;
}

.skill-box i {
    font-size: 50px;
}

.skill-box:hover {
    box-shadow: 1px 5px 30px var(--main-color);
}

.skill-box:hover .detail {
    opacity: 1;
}

.skill-box:hover .titles {
    opacity: 0;
}

@media (max-width: 1024px) {
    .skills-list {
        gap: 20px; 
        margin-left: 30px;
    }

    .skill-box {
        width: 45%; 
    }

    .titles {
        font-size: 22px; 
    }

    .detail {
        font-size: 14px; 
    }

    .skill-box i {
        font-size: 45px; 
    }
}


@media (max-width: 768px) {
    .skills-list {
        flex-direction: column; 
        align-items: center; 
        margin-left: 0; 
        gap: 30px; 
    }

    .skill-box {
        width: 80%;
    }

    .titles {
        font-size: 20px; 
    }

    .detail {
        font-size: 14px; 
    }

    .skill-box i {
        font-size: 40px; 
    }
}


.projects {
    min-height: 100vh;
    background-color: var(--second-bg-color);
}

.projects-list {
    display: flex;
    justify-content: space-between;
    gap: 20px;
    flex-wrap: wrap;
}

.projects-box {
    width: 50%; 
    height: auto; 
    background-color: transparent;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-between; 
    align-items: flex-start; 
    border: 2px solid var(--main-color);
    border-radius: 8px;
    position: relative;
    transition: transform 0.3s ease;
    margin-left: 8rem;
}

.projects-box:hover {
    transform: scale(1.05);
}

.projects-box:hover::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: linear-gradient(163deg,#002244,#002244);
    border: 2px solid var(--main-color);
    border-radius: 8px;
}

.projects-box h3 {
    color: var(--main-color);
    font-size: 24px;
    font-weight: bold;
    z-index: 1;
    margin-bottom: 10px;
}

.projects-box p {
    font-size: 14px;
    z-index: 1;
    max-width: 100%; 
    color: #fff; 
}

@media (min-width: 1028px) {
    .projects-list {
        gap: 20px;
        margin-left: 0; 
    }

    .projects-box {
        width: 70%;
        margin-left: 20;
    }

    .projects-box h3 {
        font-size: 20px; 
    }

    .projects-box p {
        font-size: 14px; 
        max-width: 100%; 
    }
}


@media (max-width: 768px) {
    .projects-list {
        flex-direction: column; 
        align-items: center; 
        gap: 30px; 
        margin-left: 0;
    }

    .projects-box {
        width: 80%; 
        margin-left: 0;
    }

    .projects-box h3 {
        font-size: 18px; 
    }

    .projects-box p {
        font-size: 16px;
        padding-left: 20px; 
        max-width: 100%; 
    }
}


.contact {
    min-height: auto;
    padding-bottom: 7rem;
    background-color: var(--bg-color);
}

.contact form {
    max-width: 50rem;
    margin: 0 auto;
    text-align: center;
}

.contact form .input-box {
    position: relative;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
}

.contact form .input-box .input-field {
    position: relative;
    width: 49%; 
    margin: .3rem 0;
}


.contact form .input-box .input-field input,
.contact form .textarea-field textarea {
    width: 100%;
    height: 100%;
    padding: 0.5rem;
    font-size: 1.6rem;
    color: var(--main-color);
    background: transparent;
    border-radius: .6rem;
    border: .2rem solid var(--main-color);
    z-index: 1;
    transition: .5s;
}

.contact form .input-box .input-field input::placeholder,
.contact form .textarea-field textarea::placeholder {
    color: var(--text-color);
}

.contact form .focus {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 0%;
    height: 100%;
    background-color: var(--second-bg-color);
    border-radius: .6rem;
    z-index: -1;
    transition: .5s;
}

.contact form .input-box .input-field input:focus~.focus,
.contact form .input-box .input-field input:valid~.focus,
.contact form .textarea-field textarea:focus~.focus,
.contact form .textarea-field textarea:valid~.focus {
    width: 100%;
}


.contact form .btn {
    margin-top: 1rem;
}

.contact form .btn .box {
    display: inline-block;
    padding: 1rem 2rem;
    font-size: 1.6rem;
    background-color: var(--main-color);
    color: var(--bg-color);
    border-radius: .6rem;
    text-decoration: none;
    transition: 0.3s;
}

.contact form .btn .box:hover {
    background-color: var(--second-bg-color);
    color: var(--main-color);
}




@media (max-width: 1024px) {
    .contact form .input-box .input-field {
        width: 100%; 
    }

    .contact form .input-box .input-field input,
    .contact form .textarea-field textarea {
        font-size: 1.4rem; 
    }

    .contact form .btn .box {
        font-size: 1.4rem; 
    }
}

@media (max-width: 768px) {
    .contact form .input-box {
        flex-direction: column; 
    }

    .contact form .input-box .input-field {
        width: 100%;
        margin-bottom: 1rem; 
    }

    .contact form .btn .box {
        width: 100%; 
    }

    .contact form .input-box .input-field input,
    .contact form .textarea-field textarea {
        font-size: 1.4rem; 
    }
}


.footer {
    background-color: var(--second-bg-color);
    color: var(--text-color);
    padding: 1rem ;
    text-align: center;
    bottom: 0;
    width: 100%;
}


.footer-bottom {
    font-size: 1.2rem;
    color: var(--text-color);
}

.footer-bottom p {
    margin: 0;
}

@media (max-width: 768px) {
    .footer {
        padding: 1.5rem 5%;
    }

    .footer-bottom {
        font-size: 1rem;
    }
}



</style>


    </head>
    <body>
        <header class="header">
        <a href="" class="logo">Selva</a>
            
        <div class='bx bx-menu' id="menu-icon"></div>
            
        <nav class="navbar">
            <a href="#Home">Home</a>
            <a href="#Skills">Skills</a>
            <a href="#Projects">Projects</a>
            <a href="#Contact">Contact</a>
        </nav>
        </header>

        <section id= "Home" class="home">
    <div class="home-content">
        <h1>Hi, I'm Selvalakshmi </h1>
        <p>Currently pursuing Bachelors in Electronics and Communication Engineering at Dr.N.G.P Institute of Technology.</p>
        <div class="btn">
            <a href="" class="box">Download CV</a>
        </div>
    </div>

    <div class="home-sci">
        <a href=""><i class='bx bxl-linkedin'></i></a>
        <a href=""><i class='bx bxl-github'></i></a>
        <a href=""><i class='bx bxl-whatsapp'></i></a>
    </div>
</section>

        
         <section id="Skills" class="skills">
            <h2 class="heading" >My <span>Skills</span></h2>
                
                <div class="skills-list">
                    <div class="skill-box">
                        <i class='bx bxl-python' style='color:#46d5f7'  ></i>
                        <h2 class="titles">Python</h2>
                        <p class="detail">Python is a high level,interpreted programming language which is known for code readability and simplicity. </p>
                    </div>
                    <div class="skill-box">
                        <i class='bx bxs-data' style='color:#46d5f7'></i>
                        <h2 class="titles">SQL</h2>
                        <p class="detail">Sql is standard programming language for maintaining and managing relational databases</p>
                    </div>
                    <div class="skill-box">
                        <i class='bx bxl-html5' style='color:#46d5f7'></i>
                        <h2 class="titles">HTML</h2>
                        <p class="detail">HTML stands for Hypertext Markup Language which provides the structure for web page</p>
                    </div>
                </div>
                
             <div class="skills-list">
                    <div class="skill-box">
                        <i class='bx bxl-flask' style='color:#46d5f7'></i>
                        <h2 class="titles">Flask</h2>
                        <p class="detail">Flask is a lightweight and flexible framework for web development and web applications that utilizes the Python programming language.</p>
                    </div>
                    <div class="skill-box">
                        <i class='bx bxl-git' style='color:#46d5f7'></i>
                        <h2 class="titles">Git</h2>
                        <p class="detail">Git is used to tracking changes in the source code, enabling multiple developers to work together on non-linear development. </p>
                    </div>
                    <div class="skill-box">
                        <i class='bx bxl-css3' style="color:#46d5f7"></i>
                        <h2 class="titles">CSS</h2>
                        <p class="detail">Sql is standard programming language for maintaining and managing relational databases</p>
                    </div>
                </div>
        </section>
        
        
        <section id="Projects" class="projects">
            <h2 class="heading" >My<span> Projects</span></h2>
            
            <div class="projects-list">
                <div class="projects-box">
                    <h3>Event registration System(ongoing)</h3>
                    <p>The Event Registration System allows users to seamlessly browse, register, and pay for upcoming events. 
                        It integrates a secure online payment gateway and automatically sends confirmation emails containing a unique ticket or secret code to users once their payment is success.
                        The backend efficiently manages user data, event details, and payments, while the front-end provides an intuitive interface for users to easily register for events.</p>
                </div>
                <div class="projects-box">
                    <h3>Productivity Tracker website</h3>
                    <p>The website is designed to give quick insights about software usage with an easy-to-navigate interface. 
                        It provides a detailed and interactive visualization of your software usage to show exactly how much time the user is spending on productive vs. unproductive tasks.
                        It displays daily productivity percentages through interactive, real-time graphs. It also contains interactive calendar which highlights productive and unproductive days through color-codes for easy reference.
                        The visual breakdown of activities helps the user to optimize your day for better productivity as well as reducing time wasted on non-essential tasks.
                    </p>
                </div>
            </div>
        </section>
        
        <section id="Contact"  class="contact">
            <h2 class="heading" >Contact <span>Me!</span></h2>
            
            <form action="/submit" method="POST">
                <div class="container1">
                <div class="input-box">
                    <div class="input-field">
                        <input type="text" placeholder="Full name" name="full_name" required>
                        <span class="focus"></span>
                    </div>
                    <div class="input-field">
                        <input type="text" placeholder="Email id" name="email_id" required>
                        <span class="focus"></span>
                    </div>
                </div>
                
                <div class="input-box">
                    <div class="input-field">
                        <input type="number" placeholder="Mobile number" name="mobile_no" required>
                        <span class="focus"></span>
                    </div>
                    <div class="input-field">
                        <input type="text" placeholder="Email subject" name="email_subject" required>
                        <span class="focus"></span>
                    </div>
                </div>
                
                <div class="textarea-field">
                    <textarea  cols="30" rows="5S" placeholder="your message" name="message" required></textarea>
                    <span class="focus"></span>
                </div>
                
                <div class="btn">
                    <button type="submit" class="box">submit</button>
                </div>
                </div>
                
            </form>  
        </section>
        
        <div class="footer">
            
    <div class="footer-bottom">
        <p>&copy; 2025 Selvalakshmi. All Rights Reserved.</p>
        
    </div>
</div>
        <script>
                // Smooth scroll effect
                document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                    anchor.addEventListener('click', function (e) {
                        e.preventDefault();

                        document.querySelector(this.getAttribute('href')).scrollIntoView({
                            behavior: 'smooth'
                        });
                    });
                });
            </script>

    </body>
</html>
