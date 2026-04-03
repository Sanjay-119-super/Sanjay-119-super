<!--- ✨ ADVANCED CREATIVE GITHUB PROFILE ✨ --->
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:00FFCC,100:0A0F2E&height=180&section=header&text=Sanjay%20Kumar&fontSize=60&fontColor=00FFCC&animation=fadeIn&fontAlignY=35" width="100%"/>
</div>

<!-- 3D Animated Glow Text (via HTML + CSS) -->
<h1 align="center" style="font-family: 'Poppins', 'JetBrains Mono', monospace; font-size: 3rem; background: linear-gradient(135deg, #00FFCC, #FF00FF, #00CCFF); -webkit-background-clip: text; -webkit-text-fill-color: transparent; animation: hueRotate 4s infinite; text-shadow: 0 0 20px rgba(0,255,204,0.5);">
  ⚡ The Code Alchemist ⚡
</h1>

<style>
  @keyframes hueRotate {
    0% { filter: hue-rotate(0deg); }
    100% { filter: hue-rotate(360deg); }
  }
  @keyframes float {
    0% { transform: translateY(0px); }
    50% { transform: translateY(-10px); }
    100% { transform: translateY(0px); }
  }
  .float-animation {
    animation: float 3s ease-in-out infinite;
  }
  .glow-card {
    transition: all 0.3s ease;
    border: 1px solid rgba(0,255,204,0.3);
    border-radius: 20px;
    background: rgba(10,15,46,0.6);
    backdrop-filter: blur(8px);
  }
  .glow-card:hover {
    transform: scale(1.02);
    box-shadow: 0 0 30px rgba(0,255,204,0.6);
    border-color: #00FFCC;
  }
</style>

<!-- Typing SVG with Matrix effect -->
<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=28&pause=800&color=00FFCC&center=true&vCenter=true&width=700&height=60&lines=Java+Backend+Maestro;Spring+Boot+Enthusiast;Microservices+Architect;Docker+%7C+Kafka+Wizard;Clean+Code+Addict;Always+Learning+%F0%9F%9A%80" />
</p>

<!-- Matrix Digital Rain Effect (Canvas based – works in GitHub) -->
<div align="center">
  <canvas id="matrixCanvas" width="800" height="120" style="border-radius: 16px; box-shadow: 0 0 20px #00FFCC;"></canvas>
</div>
<script>
  (function() {
    const canvas = document.getElementById('matrixCanvas');
    if (!canvas) return;
    const ctx = canvas.getContext('2d');
    canvas.width = 800;
    canvas.height = 120;
    const chars = "01アイウエオカキクケコサシスセソタチツテトナニヌネノハヒフヘホマミムメモヤユヨラリルレロワヲン";
    const columns = canvas.width / 20;
    const drops = [];
    for (let i = 0; i < columns; i++) drops[i] = 1;
    function draw() {
      ctx.fillStyle = 'rgba(0, 0, 0, 0.05)';
      ctx.fillRect(0, 0, canvas.width, canvas.height);
      ctx.fillStyle = '#0F0';
      ctx.font = '18px monospace';
      for (let i = 0; i < drops.length; i++) {
        const text = chars[Math.floor(Math.random() * chars.length)];
        ctx.fillText(text, i * 20, drops[i] * 20);
        if (drops[i] * 20 > canvas.height && Math.random() > 0.975) drops[i] = 0;
        drops[i]++;
      }
    }
    setInterval(draw, 50);
  })();
</script>

---

### 🧠 Tech Arsenal (Holographic Icons)
<p align="center">
  <img src="https://skillicons.dev/icons?i=java,spring,docker,kafka,maven,postman,git,aws,mysql,redis,kubernetes,grafana" />
</p>
<p align="center">
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white&labelColor=0A0F2E&color=00FFCC"/>
  <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white&labelColor=0A0F2E"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white&labelColor=0A0F2E"/>
  <img src="https://img.shields.io/badge/Kafka-231F20?style=for-the-badge&logo=apache-kafka&logoColor=white&labelColor=0A0F2E"/>
  <img src="https://img.shields.io/badge/Microservices-FF6C37?style=for-the-badge&logo=databricks&logoColor=white&labelColor=0A0F2E"/>
  <img src="https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white&labelColor=0A0F2E"/>
</p>

---

### 📈 Real-time GitHub Alchemy (Live Stats)
<div align="center" class="glow-card" style="padding: 20px; display: flex; flex-wrap: wrap; justify-content: center; gap: 15px;">
  <img src="https://github-readme-stats.vercel.app/api?username=Sanjay-119-super&show_icons=true&theme=tokyonight&hide_border=true&count_private=true&bg_color=0A0F2E&title_color=00FFCC&icon_color=00FFCC&text_color=FFFFFF" width="400" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Sanjay-119-super&layout=compact&theme=tokyonight&hide_border=true&bg_color=0A0F2E&title_color=00FFCC&text_color=FFFFFF" width="350" />
</div>
<div align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=Sanjay-119-super&theme=tokyonight&hide_border=true&background=0A0F2E&stroke=00FFCC&ring=00FFCC&fire=00FFCC&currStreakLabel=00FFCC" width="500" />
</div>

---

### 🏆 Quantum Trophies (3D Hover Effect)
<div align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=Sanjay-119-super&theme=algolia&no-frame=true&margin-w=5&column=6&bg_color=0A0F2E" />
</div>

---

### ⚡ LeetCode & GFG – Live Consciousness
<div align="center">
  <table border="0" style="border-collapse: collapse; width: 100%;">
    <tr>
      <td align="center" width="50%" style="border: 1px solid #00FFCC30; border-radius: 20px; padding: 15px;">
        <img src="https://img.shields.io/badge/LeetCode-Solved:122+-00FFCC?style=for-the-badge&logo=leetcode&logoColor=white&labelColor=0A0F2E"/>
        <br/>
        <img src="https://img.shields.io/badge/dynamic/json?style=for-the-badge&label=Easy&query=easySolved&url=https%3A%2F%2Fleetcode-stats-api.herokuapp.com%2FR0iZzo8hBw&color=green&labelColor=0A0F2E"/>
        <img src="https://img.shields.io/badge/dynamic/json?style=for-the-badge&label=Medium&query=mediumSolved&url=https%3A%2F%2Fleetcode-stats-api.herokuapp.com%2FR0iZzo8hBw&color=yellow&labelColor=0A0F2E"/>
        <img src="https://img.shields.io/badge/dynamic/json?style=for-the-badge&label=Hard&query=hardSolved&url=https%3A%2F%2Fleetcode-stats-api.herokuapp.com%2FR0iZzo8hBw&color=red&labelColor=0A0F2E"/>
        <br/>
        <img src="https://leetcode-stats-card.vercel.app/api?username=R0iZzo8hBw&theme=dark&show_icons=true&hide_border=true&bg_color=0A0F2E&text_color=FFFFFF&title_color=00FFCC" width="380"/>
      </td>
      <td align="center" width="50%" style="border: 1px solid #00FFCC30; border-radius: 20px; padding: 15px;">
        <img src="https://img.shields.io/badge/GeeksforGeeks-103%20Solved-00FFCC?style=for-the-badge&logo=geeksforgeeks&logoColor=white&labelColor=0A0F2E"/>
        <br/>
        <img src="https://img.shields.io/badge/Coding%20Score-275-brightgreen?style=for-the-badge&logo=geeksforgeeks&labelColor=0A0F2E"/>
        <br/>
        <img src="https://img.shields.io/badge/Institute%20Rank-Top%2030%25-orange?style=for-the-badge&labelColor=0A0F2E"/>
        <br/><br/>
        <img src="https://geeks-for-geeks-stats-card.vercel.app/?username=devjavarid8&layout=compact&theme=dark&bg_color=0A0F2E&title_color=00FFCC" width="380"/>
      </td>
    </tr>
  </table>
</div>

---

### 🔥 Contribution Nebula (Activity Graph)
<div align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=Sanjay-119-super&theme=react-dark&bg_color=0A0F2E&color=00FFCC&line=00FFCC&point=FFFFFF&area=true&hide_border=true" width="95%"/>
</div>

---

### 💫 Connect with the Creator
<p align="center">
  <a href="mailto:devjava.sanjay@gmail.com"><img src="https://img.shields.io/badge/-devjava.sanjay@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0A0F2E"/></a>
  <a href="https://www.linkedin.com/in/sanjayjavadev"><img src="https://img.shields.io/badge/-LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0A0F2E"/></a>
  <a href="https://github.com/Sanjay-119-super"><img src="https://img.shields.io/badge/-GitHub-181717?style=for-the-badge&logo=github&logoColor=white&labelColor=0A0F2E"/></a>
  <a href="https://x.com/SanjayJava6006"><img src="https://img.shields.io/badge/-Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white&labelColor=0A0F2E"/></a>
</p>

<!-- 3D Wave Footer -->
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:00FFCC,100:0A0F2E&height=120&section=footer&animation=twinkle"/>
</div>

<!-- Hidden Easter Egg: Console message -->
<script>
  console.log("%c🔥 You've discovered the Matrix | Sanjay's Profile | Code Alchemist 🔥", "color: #00FFCC; font-size: 16px; font-family: monospace;");
  console.log("%c⚡ Java • Spring Boot • Microservices • Docker • Kafka ⚡", "color: #FF00FF; font-size: 14px;");
</script>
