<style>
  @keyframes glowPulse {
    0%, 100% { text-shadow: 0 0 10px rgba(74, 144, 226, 0.5), 0 0 20px rgba(74, 144, 226, 0.3); }
    50% { text-shadow: 0 0 20px rgba(74, 144, 226, 0.8), 0 0 40px rgba(74, 144, 226, 0.5), 0 0 60px rgba(74, 144, 226, 0.3); }
  }
  
  @keyframes slideInDown {
    from { 
      opacity: 0;
      transform: translateY(-30px) rotateX(45deg);
    }
    to { 
      opacity: 1;
      transform: translateY(0) rotateX(0deg);
    }
  }

  @keyframes typewriter {
    from { width: 0; }
    to { width: 100%; }
  }
  
  @keyframes blink {
    0%, 50% { border-right-color: #4A90E2; }
    51%, 100% { border-right-color: transparent; }
  }
  
  @keyframes float {
    0%, 100% { transform: translateY(0px) rotateZ(0deg); }
    50% { transform: translateY(-15px) rotateZ(2deg); }
  }

  @keyframes rotateCube {
    0% { transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg); }
    100% { transform: rotateX(360deg) rotateY(360deg) rotateZ(180deg); }
  }

  @keyframes particleFloat {
    0% { opacity: 0; transform: translateY(20px); }
    50% { opacity: 1; }
    100% { opacity: 0; transform: translateY(-80px); }
  }

  .hero-container {
    perspective: 1200px;
    position: relative;
    margin-bottom: 40px;
  }

  .hero-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
  }

  .avatar-wrapper {
    position: relative;
    width: 140px;
    height: 140px;
    display: flex;
    align-items: center;
    justify-content: center;
    animation: slideInDown 1s ease-out;
  }

  .avatar-glow {
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 20px;
    background: linear-gradient(135deg, rgba(74, 144, 226, 0.3), rgba(138, 43, 226, 0.3));
    filter: blur(15px);
    animation: glowPulse 2s infinite, float 3s ease-in-out infinite;
  }

  .avatar-cube {
    position: relative;
    width: 120px;
    height: 120px;
    animation: rotateCube 20s linear infinite;
    transform-style: preserve-3d;
    z-index: 2;
  }

  .cube-face {
    position: absolute;
    width: 120px;
    height: 120px;
    background: linear-gradient(135deg, #4A90E2, #7B68EE);
    border: 2px solid rgba(74, 144, 226, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 50px;
    font-weight: bold;
    color: white;
    opacity: 0.9;
  }

  .cube-face:nth-child(1) { transform: rotateY(0deg) translateZ(60px); }
  .cube-face:nth-child(2) { transform: rotateY(90deg) translateZ(60px); }
  .cube-face:nth-child(3) { transform: rotateY(180deg) translateZ(60px); }
  .cube-face:nth-child(4) { transform: rotateY(270deg) translateZ(60px); }
  .cube-face:nth-child(5) { transform: rotateX(90deg) translateZ(60px); }
  .cube-face:nth-child(6) { transform: rotateX(-90deg) translateZ(60px); }

  .particle {
    position: absolute;
    width: 4px;
    height: 4px;
    background: #4A90E2;
    border-radius: 50%;
    animation: particleFloat 2s ease-in infinite;
  }

  .particle:nth-child(1) { left: 10%; animation-delay: 0s; }
  .particle:nth-child(2) { left: 20%; animation-delay: 0.3s; }
  .particle:nth-child(3) { left: 30%; animation-delay: 0.6s; }
  .particle:nth-child(4) { right: 30%; animation-delay: 0.9s; }
  .particle:nth-child(5) { right: 20%; animation-delay: 1.2s; }
  .particle:nth-child(6) { right: 10%; animation-delay: 1.5s; }

  .title-wrapper {
    text-align: center;
    animation: slideInDown 0.8s ease-out;
  }

  .title-wrapper h1 {
    font-size: 3.5em;
    margin: 10px 0;
    background: linear-gradient(135deg, #4A90E2 0%, #7B68EE 50%, #FF6B9D 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    letter-spacing: 2px;
    font-weight: 900;
    animation: glowPulse 2s infinite;
  }

  .subtitle {
    font-size: 1.2em;
    color: #4A90E2;
    font-weight: 600;
    animation: slideInDown 1s ease-out;
    letter-spacing: 1px;
  }

  .badge-container {
    display: flex;
    gap: 10px;
    justify-content: center;
    flex-wrap: wrap;
    animation: slideInDown 1.2s ease-out;
    margin-top: 20px;
  }

  .status-badge {
    background: rgba(74, 144, 226, 0.1);
    border: 1px solid #4A90E2;
    color: #4A90E2;
    padding: 8px 16px;
    border-radius: 20px;
    font-size: 0.9em;
    font-weight: 600;
    display: flex;
    align-items: center;
    gap: 6px;
    backdrop-filter: blur(10px);
    transition: all 0.3s ease;
  }

  .status-badge:hover {
    background: rgba(74, 144, 226, 0.2);
    transform: translateY(-3px);
    box-shadow: 0 5px 20px rgba(74, 144, 226, 0.3);
  }

  .terminal-container {
    perspective: 1200px;
    max-width: 600px;
    margin: 0 auto;
    animation: slideInDown 1.4s ease-out;
  }

  .terminal-box {
    background: linear-gradient(135deg, #0f0f1e 0%, #1a1a2e 100%);
    border: 2px solid #4A90E2;
    border-radius: 12px;
    padding: 20px;
    font-family: 'Monaco', 'Courier New', monospace;
    font-size: 14px;
    color: #00ff88;
    box-shadow: 
      0 0 20px rgba(74, 144, 226, 0.3),
      inset 0 0 20px rgba(74, 144, 226, 0.1),
      0 10px 40px rgba(0, 0, 0, 0.5);
    transform: rotateX(5deg) rotateZ(-2deg);
    transition: all 0.3s ease;
  }

  .terminal-box:hover {
    transform: rotateX(2deg) rotateZ(0deg) translateY(-5px);
    box-shadow: 
      0 0 30px rgba(74, 144, 226, 0.5),
      inset 0 0 20px rgba(74, 144, 226, 0.15),
      0 20px 60px rgba(0, 0, 0, 0.6);
  }

  .terminal-header {
    display: flex;
    gap: 8px;
    margin-bottom: 15px;
    animation: float 3s ease-in-out infinite;
  }

  .dot {
    width: 12px;
    height: 12px;
    border-radius: 50%;
    opacity: 0.7;
  }

  .dot-red { background: #ff5f57; }
  .dot-yellow { background: #febc2e; }
  .dot-green { background: #28c940; }

  .prompt {
    display: flex;
    align-items: center;
    margin: 10px 0;
    animation: slideInDown 0.6s ease-out;
  }

  .prompt-symbol {
    color: #4A90E2;
    font-weight: bold;
    margin-right: 8px;
    animation: glowPulse 2s infinite;
  }

  .command {
    animation: typewriter 1.5s steps(40, end), blink 0.75s step-end infinite;
    white-space: nowrap;
    overflow: hidden;
    border-right: 3px solid #4A90E2;
    padding-right: 5px;
  }

  .output-line {
    margin: 12px 0;
    animation: slideInDown 0.8s ease-out;
    opacity: 0.95;
  }

  .focus-items {
    display: inline-flex;
    gap: 8px;
    flex-wrap: wrap;
    justify-content: center;
    margin-top: 8px;
  }

  .focus-item {
    background: rgba(74, 144, 226, 0.15);
    border: 1px solid #4A90E2;
    border-radius: 20px;
    padding: 5px 12px;
    font-size: 12px;
    color: #4A90E2;
    animation: slideInDown 1s ease-out;
  }

  .focus-item:nth-child(1) { animation-delay: 0.2s; }
  .focus-item:nth-child(2) { animation-delay: 0.4s; }
  .focus-item:nth-child(3) { animation-delay: 0.6s; }

  .social-links {
    display: flex;
    gap: 12px;
    justify-content: center;
    animation: slideInDown 1.6s ease-out;
    margin-top: 20px;
  }

  .social-links a {
    transition: all 0.3s ease;
  }

  .social-links a:hover {
    transform: translateY(-5px);
  }
</style>

<div align="center">

<div class="hero-container">
  <div class="hero-content">
    <!-- 3D Avatar Cube -->
    <div class="avatar-wrapper">
      <div class="avatar-glow"></div>
      <div class="avatar-cube">
        <div class="cube-face">🤖</div>
        <div class="cube-face">🧠</div>
        <div class="cube-face">✨</div>
        <div class="cube-face">🔗</div>
        <div class="cube-face">📊</div>
        <div class="cube-face">⚡</div>
      </div>
      <div class="particle"></div>
      <div class="particle"></div>
      <div class="particle"></div>
      <div class="particle"></div>
      <div class="particle"></div>
      <div class="particle"></div>
    </div>

    <!-- Title Section -->
    <div class="title-wrapper">
      <h1>ADITYA RAJ</h1>
      <p class="subtitle">AI/ML Engineer</p>
      <p style="color: #888; font-size: 1em; letter-spacing: 0.5px; margin: 5px 0;">Building Predictive Models & LLM-Powered Systems</p>
    </div>

    <!-- Status Badges -->
    <div class="badge-container">
      <div class="status-badge">🧪 Building ML Models</div>
      <div class="status-badge">🔬 Exploring GenAI</div>
      <div class="status-badge">🤝 Open to Collabs</div>
    </div>
  </div>
</div>

<!-- Modern Terminal -->
<div class="terminal-container">
  <div class="terminal-box">
    <div class="terminal-header">
      <div class="dot dot-red"></div>
      <div class="dot dot-yellow"></div>
      <div class="dot dot-green"></div>
    </div>
    
    <div class="prompt">
      <span class="prompt-symbol">❯</span>
      <span class="command">whoami</span>
    </div>
    <div class="output-line">Aditya Raj • AI/ML Engineer • Bihar, India</div>
    
    <div class="prompt" style="margin-top: 15px;">
      <span class="prompt-symbol">❯</span>
      <span class="command">focus --current</span>
    </div>
    <div class="output-line">
      <div class="focus-items">
        <span class="focus-item">🧠 Machine Learning</span>
        <span class="focus-item">✨ Generative AI</span>
        <span class="focus-item">🔗 LLM Engineering</span>
      </div>
    </div>
  </div>
</div>

<!-- Social Links -->
<div class="social-links">
  <a href="https://www.linkedin.com/in/aditya-raj01/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="https://github.com/Adityaraj0021?tab=followers"><img src="https://img.shields.io/github/followers/Adityaraj0021?style=flat-square&logo=github&color=181717&label=Followers" alt="GitHub followers"/></a>
  <img src="https://img.shields.io/badge/Bihar%2C%20India-181717?style=flat-square&logo=googlemaps&logoColor=white" alt="Location"/>
</div>

</div>

<br/>

## 🧠 About Me

Somewhere between a `pandas.DataFrame` and a prompt template, I found what I actually want to build: systems that turn raw data — and now raw language — into decisions. I started with the fundamentals of ML pipelines; now I'm architecting intelligent systems powered by foundation models.

I care less about the buzzword and more about the pipeline holding together end to end: clean data in, a model that actually generalizes, and something a user can touch at the end — a churn predictor, a recommendation engine, or an agent that reasons through complex problems.

```python
class AdityaRaj:
    def __init__(self):
        self.role = "AI/ML Engineer"
        self.based_in = "Bihar, India"
        self.stack = ["Python", "PyTorch", "TensorFlow", "LangChain"]
        self.currently_exploring = ["RAG", "LLM Agents", "Vector Databases"]

    def collaborate(self, idea: str) -> bool:
        return "open-source" in idea or "AI" in idea
```

- 🧪 **Building:** predictive ML models and computer‑vision / geospatial pipelines
- 🧩 **Exploring:** RAG pipelines, LLM agents, and vector search with LangChain
- 🎯 **Core interests:** Machine Learning · Deep Learning · Computer Vision · NLP
- 🤝 **Open to:** open‑source AI/ML and GenAI collaborations
- 💬 **Ask me about:** Python, PyTorch, TensorFlow, Scikit‑learn, LangChain, Java

<br/>

## 🛠️ Tech Stack

<details open>
<summary><b>✨ Generative AI & LLM Engineering</b></summary>
<br/>

![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=000000)
![OpenAI](https://img.shields.io/badge/OpenAI%20API-412991?style=for-the-badge)
![Anthropic Claude](https://img.shields.io/badge/Anthropic%20Claude-191919?style=for-the-badge&logo=anthropic&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Google%20Gemini-886FBF?style=for-the-badge&logo=googlegemini&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-DC244C?style=for-the-badge&logo=qdrant&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Weights & Biases](https://img.shields.io/badge/Weights%20%26%20Biases-FFBE00?style=for-the-badge&logo=weightsandbiases&logoColor=000000)

<sub>Core focus: **RAG pipelines · LLM agents · prompt engineering · vector search**</sub>

</details>

<details open>
<summary><b>🤖 Machine Learning & Deep Learning</b></summary>
<br/>

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

</details>

<details>
<summary><b>☕ Languages & Backend</b></summary>
<br/>

![Java](https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)
![JUnit](https://img.shields.io/badge/JUnit-25A162?style=for-the-badge&logo=junit5&logoColor=white)

</details>

<details>
<summary><b>🔧 DevOps, Cloud & Databases</b></summary>
<br/>

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)

</details>

<br/>

## 🚀 Featured Projects

<table>
<tr>
<td width="50%" valign="top">

**[🔍 Smart Search Tool](https://github.com/Adityaraj0021/Smart_Search_tool)**
Python‑based intelligent search utility for fast, relevant information retrieval.

</td>
<td width="50%" valign="top">

**[🛰️ LULC Classification](https://github.com/Adityaraj0021/LULC_Classification)**
Land Use / Land Cover classification on satellite imagery using machine learning.

</td>
</tr>
<tr>
<td width="50%" valign="top">

**[📉 Customer Churn Prediction](https://github.com/Adityaraj0021/Churn_Customer_Prediction)**
Classification model that predicts customer churn from behavioral data.

</td>
<td width="50%" valign="top">

**[🎬 Movie Recommendation System](https://github.com/Adityaraj0021/Movie_Recommendation_System)**
Content‑based recommender system that suggests movies from user preferences.

</td>
</tr>
<tr>
<td width="50%" valign="top">

**[🪙 Gold Price Prediction](https://github.com/Adityaraj0021/Gold_prediction)**
Regression model forecasting gold prices from historical market data.

</td>
<td width="50%" valign="top">

**[🌊 Ganges Plastic Interceptor](https://github.com/Adityaraj0021/JaipurIndia_GangesRiverPlasticInterceptor)**
Environmental‑tech collaboration on plastic interception — Jaipur, India chapter.

</td>
</tr>
</table>

<br/>

## 📊 GitHub Analytics

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=Adityaraj0021&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" alt="Aditya's GitHub stats"/>
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Adityaraj0021&layout=compact&theme=tokyonight&hide_border=true" alt="Top Languages"/>

<img src="https://streak-stats.demolab.com/?user=Adityaraj0021&theme=tokyonight&hide_border=true" alt="GitHub Streak"/>

</div>

<br/>

## 🤝 Let's Connect

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/aditya-raj01/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Adityaraj0021)

</div>

<div align="center">

*"Turning data into decisions, one model at a time."*

</div>
