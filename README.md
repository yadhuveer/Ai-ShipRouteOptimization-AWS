**🚢 AI-ShipPlanner – Intelligent Voyage Optimization System**  
**📌 Overview**

AI-ShipPlanner is an **intelligent shipping optimization platform** that predicts the best maritime route for a cargo ship based on origin, destination, cargo load, weather, traffic conditions ,ETA, Fuel Consumption and has **ML Model retrain feature to Retrain the Model to keep model Updated**

It combines **graph algorithms (Yen’s + Dijkstra)**, **real-time APIs to find Weather and traffic conditions**, **machine learning models**, and **caching strategies** to deliver an optimized path with ETA, fuel consumption, and performance score.


This project is **end-to-end designed and implemented by me, showcasing expertise in full-stack development, ML integration, and scalable system design**.



<br>
<br>

✨ Key Features

✅ **User Authentication (JWT)** – Secure login/logout, only authenticated users can search for routes  
✅ **Role-Based Authorization** – Only Admin can retrain ML models  
✅ **Shortest Path Finder** – Yen’s Algorithm (K-shortest paths based on Dijkstra)  
✅ **Real-Time Weather & Traffic Data** – Integrated via APIs  
✅ **Machine Learning Models**  
     📌**Fuel Consumption Prediction** – Linear Regression  
     📌**ETA Prediction** – Linear Regression  
     📌**Route Scoring** – Random Forest Regressor (considers ETA, fuel, traffic, distance)  
✅ **Optimized Path Recommendation** – Chooses best path based on model score  
✅ **Caching with Redis (or in-memory fallback)** – Avoids recomputing shortest paths  
✅ **Rate Limiting** – Users can make max 10 optimized path searches/day  
✅ **User Feedback Loop** – Users can provide actual ETA & fuel usage for retraining  
✅ **Admin Retraining** – Admin can retrain ML models with selected feedback data  
✅ **Search History** – Users can view past voyage optimizations  




🏗️ System Architecture

```
text
[ Next.js UI ]  --->  [ Node.js Backend ]  --->  [ FastAPI ML Service ]  
       |                    |                               |  
   User Input           Auth, Rate Limit,           ML Models (Fuel, ETA,  
(origin, dest, cargo)         Routing            Score) + APIs (Weather, Traffic),Caching  
       |                        |                           |  
       <------------------- Optimized Path (ETA, Fuel, Score, Route) -------->
```
<br>
<br>

**🛠️ Tech Stack**


**🌐 Frontend**
📌Next.js – User interface
📌Tailwind CSS – Styling

**⚙️ Backend**
📌Node.js + Express – API Gateway, Auth, Rate Limiting,
📌Redis (planned) / In-memory cache – Shortest path caching

**🤖 Machine Learning (FastAPI)**
📌FastAPI – Serving ML models,  Caching
📌scikit-learn – Linear Regression, Random Forest
📌Dijkstra & Yen’s Algorithm – Shortest path calculation

**📡 External APIs**
📌Weather API (real-time conditions)
📌Traffic API (real-time condition and currently generic, planned to integrate with Marine Traffic API)

**🗄️ Database**

 📌MongoDB – User data, search history, feedback


<br>
<br>

📊 Example Workflow  
 📌User logs in → provides **Origin, Destination, Cargo**  
 📌Node.js → sends req to FastAPI  
 📌FastAPI → shortest five path, **caching**, **computes ETA, Fuel, Score for each path and provides best path**.  
 📌Node.js → **rate-limiting, and sends results back**  
 📌UI → displays best path, ETA, Fuel, Traffic,Speed, Route  
 📌User → can give **feedback (actual ETA/actual Fuel used)**  
 📌Admin → **retrains ML model with feedback**  

 <br>

🔒 Authentication & Authorization  
 📌JWT Auth – Protects all voyage search endpoints  
 📌Authorization – Only Admin role can retrain models  

<br>

 📈 Future Improvements    
   ✅ Integrate Marine Traffic API for real-time shipping traffic            

<br>

🧑‍💻 Author    
👤 [Yadhuveer H S]    
💼 Aspiring Full Stack Developer | MERN + FastAPI + ML Enthusiast | Next.js, NEST    
📫 Reach me at: [yadhuveeryadu@gmail.com] | [www.linkedin.com/in/yadhuveer-h-s-06212b215]    
