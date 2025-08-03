<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>โปรไฟล์ GitHub - Somsak Meesangpetch</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Sarabun:wght@400;500;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Warm Neutrals with Teal Accent -->
    <!-- Application Structure Plan: A single-page, top-down layout was chosen to create an intuitive and familiar user flow for a personal profile. The structure progresses logically from a general introduction (who is this person?) to specific details (highlights, achievements, projects, and stats). This linear narrative helps users quickly understand the developer's skills and experience without complex navigation. Interactive elements like hover effects and a dynamic chart are added to enhance engagement. -->
    <!-- Visualization & Content Choices: Report Info: GitHub stats and project languages. Goal: Showcase skills and activity. Viz/Presentation Method: 1) Embedded image for overall stats (from github-readme-stats) for consistency with the GitHub ecosystem. 2) A dynamic Donut Chart (Chart.js) for language distribution. Interaction: Hovering over chart segments reveals details. Justification: The donut chart provides a quick, visually appealing summary of technical skills, which is more engaging than a static list. Library/Method: Chart.js (Canvas). -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Sarabun', sans-serif;
            background-color: #f8f7f4; /* Warm neutral background */
            color: #3d3d3d;
        }
        .card {
            background-color: #ffffff;
            border-radius: 1rem;
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
            transition: all 0.3s ease-in-out;
        }
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -2px rgb(0 0 0 / 0.1);
        }
        .accent-color {
            color: #14b8a6; /* Teal */
        }
        .bg-accent {
            background-color: #14b8a6;
        }
        .border-accent {
            border-color: #14b8a6;
        }
    </style>
</head>
<body>

    <main class="container mx-auto max-w-4xl p-4 sm:p-8">

        <!-- Header Section -->
        <header class="text-center mb-12">
            <img src="https://avatars.githubusercontent.com/u/4925769?v=4" alt="โปรไฟล์" class="w-32 h-32 rounded-full mx-auto mb-4 border-4 border-white shadow-lg">
            <h1 class="text-4xl md:text-5xl font-bold text-gray-800">Somsak Meesangpetch</h1>
            <p class="text-xl text-gray-500 mt-1">@ssomsakth</p>
            <p class="max-w-2xl mx-auto text-gray-600 mt-4 text-lg">
                นักพัฒนาซอฟต์แวร์ที่มีความมุ่งมั่นในการสร้างสรรค์โปรเจกต์โอเพนซอร์ส และมีส่วนร่วมในชุมชนนักพัฒนา
            </p>
        </header>

        <!-- Highlights Section -->
        <section class="mb-12">
            <h2 class="text-3xl font-bold text-center mb-2">🌟 จุดเด่น</h2>
            <p class="text-center text-gray-500 mb-8">นี่คือทักษะและความสามารถหลักที่ผมภาคภูมิใจนำเสนอ</p>
            <div class="grid md:grid-cols-3 gap-6 text-center">
                <div class="card p-6">
                    <p class="text-5xl mb-3">👥</p>
                    <h3 class="text-xl font-bold mb-2">ชุมชนนักพัฒนา</h3>
                    <p class="text-gray-600">มีส่วนร่วมและสร้างเครือข่ายกับนักพัฒนาคนอื่นๆ</p>
                </div>
                <div class="card p-6">
                    <p class="text-5xl mb-3">💻</p>
                    <h3 class="text-xl font-bold mb-2">ทักษะการเขียนโค้ด</h3>
                    <p class="text-gray-600">เชี่ยวชาญด้าน JavaScript และ Python</p>
                </div>
                <div class="card p-6">
                    <p class="text-5xl mb-3">⭐</p>
                    <h3 class="text-xl font-bold mb-2">โปรเจกต์ยอดนิยม</h3>
                    <p class="text-gray-600">โปรเจกต์ที่ได้รับความสนใจกว่า 1,000 ดาว</p>
                </div>
            </div>
        </section>

        <!-- Achievements Section -->
        <section class="mb-12">
            <h2 class="text-3xl font-bold text-center mb-2">🏆 ความสำเร็จ</h2>
            <p class="text-center text-gray-500 mb-8">รางวัลและความสำเร็จที่เป็นเครื่องยืนยันถึงความทุ่มเทในการทำงาน</p>
            <div class="space-y-4 max-w-2xl mx-auto">
                <div class="card p-4 flex items-center">
                    <span class="text-3xl mr-4">🏅</span>
                    <div>
                        <h3 class="font-bold text-lg">นักพัฒนา GitHub ระดับยอดเยี่ยม</h3>
                        <p class="text-gray-600">ได้รับรางวัลจากความมุ่งมั่นในการทำโปรเจกต์โอเพนซอร์ส</p>
                    </div>
                </div>
                <div class="card p-4 flex items-center">
                    <span class="text-3xl mr-4">🚀</span>
                    <div>
                        <h3 class="font-bold text-lg">Contributor 100 โปรเจกต์</h3>
                        <p class="text-gray-600">มีส่วนร่วมในโปรเจกต์โอเพนซอร์สมากกว่า 100 โปรเจกต์</p>
                    </div>
                </div>
                <div class="card p-4 flex items-center">
                    <span class="text-3xl mr-4">🌍</span>
                    <div>
                        <h3 class="font-bold text-lg">ผู้นำชุมชนโอเพนซอร์ส</h3>
                        <p class="text-gray-600">สร้างและดูแลชุมชนนักพัฒนาโอเพนซอร์ส</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Featured Projects Section -->
        <section class="mb-12">
            <h2 class="text-3xl font-bold text-center mb-2">📂 โปรเจกต์เด่น</h2>
            <p class="text-center text-gray-500 mb-8">ตัวอย่างผลงานบางส่วนที่ผมได้พัฒนาขึ้น คลิกเพื่อดูรายละเอียดเพิ่มเติมบน GitHub</p>
            <div class="grid md:grid-cols-2 gap-6">
                <a href="https://github.com/ssomsakth/project-name-1" target="_blank" rel="noopener noreferrer" class="card p-6 block">
                    <h3 class="text-xl font-bold accent-color mb-2">project-name-1</h3>
                    <p class="text-gray-600 mb-4">คำอธิบายโปรเจกต์... ที่นี่คือรายละเอียดสั้นๆ เกี่ยวกับโปรเจกต์นี้</p>
                    <div class="flex justify-between items-center text-sm text-gray-500">
                        <span>ภาษา: JavaScript</span>
                        <span>⭐ 500</span>
                    </div>
                </a>
                <a href="https://github.com/ssomsakth/project-name-2" target="_blank" rel="noopener noreferrer" class="card p-6 block">
                    <h3 class="text-xl font-bold accent-color mb-2">project-name-2</h3>
                    <p class="text-gray-600 mb-4">คำอธิบายโปรเจกต์... ที่นี่คือรายละเอียดสั้นๆ เกี่ยวกับโปรเจกต์นี้</p>
                    <div class="flex justify-between items-center text-sm text-gray-500">
                        <span>ภาษา: Python</span>
                        <span>⭐ 300</span>
                    </div>
                </a>
            </div>
        </section>

        <!-- Stats Section -->
        <section>
            <h2 class="text-3xl font-bold text-center mb-2">📊 สถิติ</h2>
            <p class="text-center text-gray-500 mb-8">ภาพรวมกิจกรรมและสัดส่วนภาษาที่ใช้ในการพัฒนาโปรเจกต์บน GitHub</p>
            <div class="grid md:grid-cols-2 gap-8 items-center">
                <div class="card p-6">
                    <h3 class="font-bold text-xl text-center mb-4">สถิติโดยรวม</h3>
                    <img src="https://github-readme-stats.vercel.app/api?username=ssomsakth&show_icons=true&theme=default&hide_border=true&border_radius=10&hide_rank=true" alt="GitHub Stats">
                </div>
                <div class="card p-6">
                    <h3 class="font-bold text-xl text-center mb-4">สัดส่วนภาษาที่ใช้</h3>
                    <div class="chart-container relative h-64 md:h-80 w-full max-w-sm mx-auto">
                        <canvas id="languageChart"></canvas>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer class="text-center p-6 mt-8">
        <p class="text-gray-500">สร้างสรรค์จากโปรไฟล์ GitHub ของ Somsak Meesangpetch</p>
    </footer>

    <script>
        const ctx = document.getElementById('languageChart').getContext('2d');
        const languageChart = new Chart(ctx, {
            type: 'doughnut',
            data: {
                labels: ['JavaScript', 'Python', 'อื่น ๆ'],
                datasets: [{
                    label: 'สัดส่วนภาษา',
                    data: [60, 30, 10],
                    backgroundColor: [
                        '#f59e0b', // Amber
                        '#3b82f6', // Blue
                        '#d1d5db'  // Gray
                    ],
                    borderColor: '#ffffff',
                    borderWidth: 4
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: {
                        position: 'bottom',
                    },
                    tooltip: {
                        callbacks: {
                            label: function(context) {
                                let label = context.label || '';
                                if (label) {
                                    label += ': ';
                                }
                                if (context.parsed !== null) {
                                    label += context.parsed + '%';
                                }
                                return label;
                            }
                        }
                    }
                }
            }
        });
    </script>

</body>
</html>
