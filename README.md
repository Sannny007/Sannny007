<div align="center">

# Sanny Kumar Sharma

</div>

<!-- 3D Animated Header Background -->
<canvas id="3dCanvas" width="1200" height="250" style="width: 100%; max-width: 1200px; display: block; margin: 30px auto; border-radius: 20px; background: linear-gradient(135deg, rgba(99,102,241,0.2) 0%, rgba(0,102,255,0.1) 100%);"></canvas>

<script>
const canvas3d = document.getElementById('3dCanvas');
if (canvas3d) {
  const ctx = canvas3d.getContext('2d');
  const w = canvas3d.width;
  const h = canvas3d.height;
  
  // 3D Cube Animation
  class Cube3D {
    constructor(x, y, z) {
      this.x = x;
      this.y = y;
      this.z = z;
      this.rx = 0;
      this.ry = 0;
      this.rz = 0;
      this.size = 40;
    }
    
    rotate() {
      this.rx += 0.01;
      this.ry += 0.015;
      this.rz += 0.008;
    }
    
    getProjection() {
      const cos_rx = Math.cos(this.rx);
      const sin_rx = Math.sin(this.rx);
      const cos_ry = Math.cos(this.ry);
      const sin_ry = Math.sin(this.ry);
      const cos_rz = Math.cos(this.rz);
      const sin_rz = Math.sin(this.rz);
      
      const vertices = [
        [-1, -1, -1], [1, -1, -1], [1, 1, -1], [-1, 1, -1],
        [-1, -1, 1], [1, -1, 1], [1, 1, 1], [-1, 1, 1]
      ];
      
      const rotated = vertices.map(v => {
        let x = v[0], y = v[1], z = v[2];
        
        let y1 = y * cos_rx - z * sin_rx;
        let z1 = y * sin_rx + z * cos_rx;
        
        let x2 = x * cos_ry + z1 * sin_ry;
        let z2 = -x * sin_ry + z1 * cos_ry;
        
        let x3 = x2 * cos_rz - y1 * sin_rz;
        let y3 = x2 * sin_rz + y1 * cos_rz;
        
        return [x3 * this.size + this.x, y3 * this.size + this.y, z2 * this.size + this.z];
      });
      
      return rotated.map(v => ({
        x: v[0] + w / 2,
        y: v[1] + h / 2,
        z: v[2]
      }));
    }
  }
  
  const cubes = [
    new Cube3D(-150, 0, 0),
    new Cube3D(0, 0, 0),
    new Cube3D(150, 0, 0)
  ];
  
  function drawCube(points) {
    ctx.strokeStyle = 'rgba(99, 102, 241, 0.8)';
    ctx.lineWidth = 2;
    
    const edges = [
      [0, 1], [1, 2], [2, 3], [3, 0],
      [4, 5], [5, 6], [6, 7], [7, 4],
      [0, 4], [1, 5], [2, 6], [3, 7]
    ];
    
    edges.forEach(edge => {
      const p1 = points[edge[0]];
      const p2 = points[edge[1]];
      ctx.beginPath();
      ctx.moveTo(p1.x, p1.y);
      ctx.lineTo(p2.x, p2.y);
      ctx.stroke();
    });
    
    ctx.fillStyle = 'rgba(0, 102, 255, 0.1)';
    points.forEach(p => {
      ctx.beginPath();
      ctx.arc(p.x, p.y, 3, 0, Math.PI * 2);
      ctx.fill();
    });
  }
  
  function animate3d() {
    ctx.fillStyle = 'rgba(15, 23, 42, 0.05)';
    ctx.fillRect(0, 0, w, h);
    
    cubes.forEach(cube => {
      cube.rotate();
      const projection = cube.getProjection();
      drawCube(projection);
    });
    
    requestAnimationFrame(animate3d);
  }
  
  animate3d();
}
</script>

<!-- Dynamic Typing Animation -->
<img src="https://readme-typing-svg.herokuapp.com?font=Poppins&weight=900&size=40&duration=3000&pause=800&color=6366F1&center=true&vCenter=true&width=900&lines=PROFESSIONAL+FULL+STACK+DEVELOPER;FRONTEND+ARCHITECT;3D+WEB+INNOVATOR;CREATIVE+TECHNOLOGIST" alt="Typing SVG"/>

<br/>

**✨ Transforming Ideas Into Interactive 3D Experiences ✨**

---

## 🏆 Core Components

<div align="center">

### Frontend Layer
```javascript
🎨 React 18 + TypeScript
🔄 Redux Toolkit State Management
⚡ Next.js Server-Side Rendering
🎯 Custom React Hooks
📱 Responsive Component Architecture
```

### Backend Layer
```javascript
🚀 Node.js + Express.js
🔐 Authentication & Security
📡 RESTful & GraphQL APIs
🗄️ MongoDB & PostgreSQL
⚙️ Middleware & Business Logic
```

### 3D & Animation Layer
```javascript
🎬 Three.js 3D Graphics
✨ GSAP Advanced Animations
🌊 Framer Motion Components
🎨 Canvas & WebGL
🔥 Interactive Visualizations
```

</div>

---

## 🛠️ Technical Stack (Scrolling Showcase)

<div align="center">

<style>
  @keyframes scroll-tech {
    0% { transform: translateX(100%); }
    100% { transform: translateX(-100%); }
  }
  
  .tech-scroll {
    display: flex;
    animation: scroll-tech 25s linear infinite;
    white-space: nowrap;
    gap: 20px;
    padding: 20px;
  }
  
  .tech-item {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: linear-gradient(135deg, rgba(99,102,241,0.15) 0%, rgba(0,102,255,0.1) 100%);
    padding: 12px 20px;
    border-radius: 25px;
    border: 1px solid rgba(99,102,241,0.3);
    font-weight: 600;
    color: #6366F1;
    font-size: 14px;
  }
</style>

<div class="tech-scroll">
  <div class="tech-item">⚛️ React 18</div>
  <div class="tech-item">📘 TypeScript</div>
  <div class="tech-item">🔄 Redux Toolkit</div>
  <div class="tech-item">🎬 GSAP</div>
  <div class="tech-item">🎨 Three.js</div>
  <div class="tech-item">💨 Tailwind CSS</div>
  <div class="tech-item">🚀 Next.js</div>
  <div class="tech-item">🟢 Node.js</div>
  <div class="tech-item">📦 Express.js</div>
  <div class="tech-item">🍃 MongoDB</div>
  <div class="tech-item">🐘 PostgreSQL</div>
  <div class="tech-item">🌊 Framer Motion</div>
  <div class="tech-item">🎨 Canvas API</div>
  <div class="tech-item">🔧 GraphQL</div>
  <div class="tech-item">⚡ WebGL</div>
</div>

</div>

---

## 🎯 Frontend Technologies

![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Redux](https://img.shields.io/badge/Redux_Toolkit-764ABC?style=for-the-badge&logo=redux&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)

---

## 🎬 3D & Animation Stack

![Three.js](https://img.shields.io/badge/Three.js-000000?style=for-the-badge&logo=three.js&logoColor=white)
![GSAP](https://img.shields.io/badge/GSAP-88CE02?style=for-the-badge&logo=greensock&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer_Motion-0055FF?style=for-the-badge&logo=framer&logoColor=white)
![Canvas](https://img.shields.io/badge/Canvas_API-FF6B00?style=for-the-badge&logo=html5&logoColor=white)
![WebGL](https://img.shields.io/badge/WebGL-990000?style=for-the-badge&logo=webgl&logoColor=white)

---

## 🔧 Backend & Database

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-13AA52?style=for-the-badge&logo=mongodb&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![GraphQL](https://img.shields.io/badge/GraphQL-E10098?style=for-the-badge&logo=graphql&logoColor=white)

---

## ⚡ Developer Tools

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![VS Code](https://img.shields.io/badge/VS_Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

---

## 🌟 Key Specializations

<div align="center">

| 🎨 **Frontend** | 🎬 **3D/Animation** | 🔧 **Backend** | ⚡ **Performance** |
|:---:|:---:|:---:|:---:|
| React Mastery | Three.js Scenes | Scalable APIs | Optimization |
| State Management | GSAP Animations | Database Design | Code Splitting |
| Responsive Design | Interactive Graphics | Authentication | Caching |
| TypeScript | Motion Effects | Microservices | SEO |

</div>

---

## 📊 GitHub Stats

<div align="center">

![Profile Views](https://komarev.com/ghpvc/?username=Sannny007&style=flat-square&color=6366F1)

</div>

---

## 🤝 Connect

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/sannny007)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Sannny007)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sanny433sharma@gmail.com)

</div>

---

<div align="center">

### 💡 Building Tomorrow's Web Today

*Specializing in high-performance full-stack applications with immersive 3D experiences*

</div>