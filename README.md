<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>พอร์ตโฟลิโอแนะนำตัวเอง | My Portfolio</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Sarabun:wght@300;400;600;700&display=swap" rel="stylesheet">

    <style>
        /* --- ตั้งค่าพื้นฐาน (Reset & Global Styles) --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth; /* เลื่อนหน้าจอแบบนุ่มนวล */
        }

        body {
            font-family: 'Sarabun', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: #212121;
            background-color: #FFFFFF;
            line-height: 1.6;
        }

        section {
            padding: 80px 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
        }

        .container {
            max-width: 800px;
            width: 100%;
            text-align: center;
        }

        h2 {
            font-size: 2.5rem;
            margin-bottom: 30px;
            color: #2196F3;
            position: relative;
            display: inline-block;
        }

        h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 4px;
            background-color: #2196F3;
            border-radius: 2px;
        }

        /* --- แถบเมนูด้านบน (Sticky Navbar) --- */
        .navbar {
            position: sticky;
            top: 0;
            background-color: #FFFFFF;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            display: flex;
            justify-content: center;
            padding: 15px 0;
        }

        .navbar a {
            color: #2196F3;
            text-decoration: none;
            margin: 0 15px;
            font-weight: 600;
            font-size: 1.1rem;
            transition: color 0.3s ease;
        }

        .navbar a:hover {
            color: #0B7BDA;
        }

        /* --- ส่วนหัว (Header/Hero) --- */
        #hero {
            background: linear-gradient(135deg, #E3F2FD 0%, #FFFFFF 100%);
            padding-top: 120px;
        }

        .profile-img {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            object-fit: cover;
            border: 5px solid #2196F3;
            box-shadow: 0 8px 20px rgba(33, 150, 243, 0.2);
            margin-bottom: 25px;
        }

        #hero h1 {
            font-size: 3rem;
            color: #2196F3;
            margin-bottom: 10px;
        }

        .tagline {
            font-size: 1.3rem;
            color: #666;
            font-weight: 300;
        }

        /* --- ส่วนประวัติย่อ (About Me) --- */
        #about {
            background-color: #FFFFFF;
        }

        .about-text {
            font-size: 1.2rem;
            max-width: 650px;
            margin: 0 auto;
            color: #444;
            text-align: justify;
            text-justify: inter-word;
        }

        /* --- ส่วนความสามารถพิเศษ (Skills) --- */
        #skills {
            background-color: #E3F2FD;
        }

        .skills-container {
            max-width: 600px;
            width: 100%;
            margin: 0 auto;
            text-align: left;
        }

        .skill-box {
            margin-bottom: 20px;
        }

        .skill-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-weight: 600;
        }

        .progress-bar {
            width: 100%;
            height: 15px;
            background-color: #FFFFFF;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: inset 0 1px 3px rgba(0,0,0,0.1);
        }

        .progress {
            height: 100%;
            background-color: #2196F3;
            width: 0; /* เริ่มต้นที่ 0 เพื่อให้ JS สั่งขยายอนิเมชัน */
            border-radius: 10px;
            transition: width 1.5s cubic-bezier(0.1, 0.8, 0.2, 1);
        }

        /* --- ส่วนช่องทางติดต่อ (Contact) --- */
        #contact {
            background-color: #FFFFFF;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 40px;
            flex-wrap: wrap;
        }

        .contact-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            color: #2196F3;
            text-decoration: none;
            font-weight: 600;
            transition: transform 0.3s ease, color 0.3s ease;
        }

        .contact-item svg, .contact-item .icon {
            width: 50px;
            height: 50px;
            fill: currentColor;
            font-size: 3rem;
            margin-bottom: 10px;
        }

        /* Hover Effect */
        .contact-item:hover {
            transform: translateY(-8px);
            color: #0B7BDA;
        }

        /* --- การรองรับหน้าจอมือถือ (Responsive Design) --- */
        @media (max-width: 768px) {
            .navbar {
                padding: 10px 0;
            }
            .navbar a {
                margin: 0 10px;
                font-size: 0.95rem;
            }
            #hero h1 {
                font-size: 2.2rem;
            }
            .tagline {
                font-size: 1.1rem;
            }
            h2 {
                font-size: 2rem;
            }
            .contact-links {
                flex-direction: column;
                gap: 25px;
            }
        }
    </style>
</head>
<body>

    <nav class="navbar">
        <a href="#hero">หน้าแรก</a>
        <a href="#about">ประวัติย่อ</a>
        <a href="#skills">ทักษะ</a>
        <a href="#contact">ติดต่อ</a>
    </nav>

    <section id="hero">
        <div class="container">
            <img src="https://placehold.co/200x200/2196F3/ffffff?text=My+Profile" alt="Profile Picture" class="profile-img">
            <h1>สมชาย ดีใจ</h1>
            <p class="tagline">Frontend Developer & UX/UI Enthusiast</p>
        </div>
    </section>

    <section id="about">
        <div class="container">
            <h2>ประวัติย่อ</h2>
            <div class="about-text">
                <p>สวัสดีครับ ผมเป็นนักพัฒนาเว็บไซต์รุ่นใหม่ที่หลงใหลในการเขียนโค้ดและสร้างสรรค์ User Experience ที่ดีเยี่ยม มีความสนใจในเทคโนโลยีเว็บสมัยใหม่และการออกแบบที่เรียบง่ายแต่ทรงพลัง เป้าหมายของผมคือการพัฒนาซอฟต์แวร์ที่สามารถช่วยแก้ปัญหาในชีวิตประจำวันของผู้คน และพร้อมที่จะเรียนรู้สิ่งใหม่ๆ ร่วมกับทีมที่มีไฟเพื่อพัฒนาตนเองอย่างต่อเนื่องในสายงานนี้ครับ</p>
            </div>
        </div>
    </section>

    <section id="skills">
        <div class="container">
            <h2>ความสามารถพิเศษ</h2>
            <div class="skills-container">
                
                <div class="skill-box">
                    <div class="skill-info">
                        <span>HTML5 / CSS3</span>
                        <span>90%</span>
                    </div>
                    <div class="progress-bar">
                        <div class="progress" data-percent="90%"></div>
                    </div>
                </div>

                <div class="skill-box">
                    <div class="skill-info">
                        <span>JavaScript (ES6+)</span>
                        <span>80%</span>
                    </div>
                    <div class="progress-bar">
                        <div class="progress" data-percent="80%"></div>
                    </div>
                </div>

                <div class="skill-box">
                    <div class="skill-info">
                        <span>Responsive Design</span>
                        <span>85%</span>
                    </div>
                    <div class="progress-bar">
                        <div class="progress" data-percent="85%"></div>
                    </div>
                </div>

                <div class="skill-box">
                    <div class="skill-info">
                        <span>React.js</span>
                        <span>70%</span>
                    </div>
                    <div class="progress-bar">
                        <div class="progress" data-percent="70%"></div>
                    </div>
                </div>

                <div class="skill-box">
                    <div class="skill-info">
                        <span>Git & GitHub</span>
                        <span>75%</span>
                    </div>
                    <div class="progress-bar">
                        <div class="progress" data-percent="75%"></div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <section id="contact">
        <div class="container">
            <h2>ช่องทางติดต่อ</h2>
            <div class="contact-links">
                
                <a href="mailto:somchai.dee@email.com" class="contact-item">
                    <svg viewBox="0 0 24 24">
                        <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
                    </svg>
                    <span>somchai.dee@email.com</span>
                </a>

                <a href="tel:0812345678" class="contact-item">
                    <span class="icon">📞</span>
                    <span>081-234-5678</span>
                </a>

                <a href="https://github.com" target="_blank" class="contact-item">
                    <svg viewBox="0 0 24 24">
                        <path d="M12 2A10 10 0 0 0 2 12c0 4.42 2.87 8.17 6.84 9.5.5.08.66-.23.66-.5v-1.69c-2.77.6-3.36-1.34-3.36-1.34-.46-1.16-1.11-1.47-1.11-1.47-.9-.62.07-.6.07-.6 1 .07 1.53 1.03 1.53 1.03.9 1.52 2.34 1.07 2.91.83.1-.65.35-1.09.63-1.34-2.22-.25-4.55-1.11-4.55-4.94 0-1.1.38-2 1.03-2.71-.1-.25-.45-1.29.1-2.64 0 0 .84-.27 2.75 1.02.79-.22 1.65-.33 2.5-.33.85 0 1.71.11 2.5.33 1.91-1.29 2.75-1.02 2.75-1.02.55 1.35.2 2.39.1 2.64.65.71 1.03 1.6 1.03 2.71 0 3.84-2.34 4.68-4.57 4.93.36.31.68.92.68 1.85V21c0 .27.16.59.67.5C19.14 20.16 22 16.42 22 12A10 10 0 0 0 12 2z"/>
                    </svg>
                    <span>GitHub Profile</span>
                </a>

            </div>
        </div>
    </section>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // ดึงข้อมูล Progress bar ทั้งหมด
            const progressBars = document.querySelectorAll('.progress');
            
            // ใช้ setTimeout เล็กน้อยเพื่อให้เบราว์เซอร์พร้อมแสดงผลแอนิเมชันหลังจากโหลดหน้าสำเร็จ
            setTimeout(() => {
                progressBars.forEach(bar => {
                    // ดึงค่าเปอร์เซ็นต์จาก attribute 'data-percent' มากำหนดความกว้าง (width) ของ CSS
                    const targetWidth = bar.getAttribute('data-percent');
                    bar.style.width = targetWidth;
                });
            }, 200);
        });
    </script>
</body>
</html>
