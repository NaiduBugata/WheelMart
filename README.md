# **WheelMart**

---

### **Chosen Problem Statement**
**Build a Two-Wheeler Marketplace Web App**  
_Given by Vahan Bazar_

---

### **Reason for Choosing Problem Statement**
We chose this problem statement because the two-wheeler market is one of the largest and fastest-growing segments in India. However, the online buying and selling experience is still broken. Buyers use scattered sources, leading to inefficiency and lack of trust.

---

### **Suggested Method**
- **Frontend:** Created with **React** for a responsive user interface.
- **Backend:** Built using **Flask** connected with **MongoDB** to maintain listing information, users, and dealers.

---

### **Major Features / Modules**
1. **Showcase**: Present big photos, name, and price for EVs, bikes, and scooters.
2. **Search & Filters**: Filter results by brand, price, fuel type, mileage, etc.
3. **Product Page**: Comprehensive features, pictures, discount rates, and prices for the product.
4. **Model Comparison**: Side-by-side comparisons of two or more vehicles.
5. **Financial Tools**: Calculate **EMI** and fuel costs.
6. **Used Bikes**: Show or provide *verified* used bikes for sale.
7. **Showrooms & Test Rides**: Dealer list and scheduling for test rides.
8. **AI Chatbot**: Answer common queries.
9. **Price Predictor**: Predict fair price for bike sellers.

---

### **System Architecture**

**Architecture Diagram / Workflow**  
![WhatsApp Image 2025-09-28 at 18 51 49_937cb12e](https://github.com/user-attachments/assets/0dbe164f-280b-461f-b6f6-4741070220d6)  
<img width="264" height="530" alt="image" src="https://github.com/user-attachments/assets/f886cfbc-5aa2-4047-9214-07f56fa824a5" />

---

#### **Explanation of Data Flow**
1. The data flow begins at the **frontend** where users browse, filter, and view product details via a **React** UI.
2. Requests are sent to the **backend** (**Flask**), where business logic is processed and information is updated or retrieved.
3. Data is persisted in the **database** (MongoDB), optimized for fast search and retrieval of listings, users, dealers, bookings, and reviews.
4. **External services**: Google Maps API for showroom maps, payment gateways for bookings and dealer subscriptions.
5. Responses are processed at the UI as **JSON** data and rendered as user-friendly interfaces.

---

### **Technology Stack**

**Frontend:**  
- React.js: Dynamic and responsive UI  
- Material UI / TailwindCSS / CSS: Modern styling

**Backend:**  
- Flask (Python): Lightweight backend framework for APIs and business logic  
- REST APIs: Communication between frontend and backend

**Database:**  
- MongoDB: NoSQL database to store vehicle listings, users, dealers, bookings, reviews

**Machine Learning:**  
- Price Predictor: ML model to predict used bike prices  
- Libraries: Scikit-learn, Pandas, NumPy

**AI Features:**  
- Chatbot Assistant: AI bot for browsing, comparison, EMI, recommendations  
- Libraries/Services: OpenAI API / Rasa / Transformers

**APIs & External Libraries:**  
- Google Maps API – Showroom locations and directions  
- Payment Gateway API – Bookings & dealer subscriptions  
- SMTP / Twilio API – Notifications (email/SMS)  
- Axios / Fetch – API calls from frontend  
- JWT Authentication – Secure logins & dealer dashboards

---

### **Algorithms & Models**

**Selected Algorithms and Justification:**  
1. **RAG-Powered Chatbot (Text & Web):**  
   - Retrieval-Augmented Generation for contextual, accountable responses.
2. **AI Voice Assistant (Calls):**  
   - Speech-to-Text, NLP, and Text-to-Speech to automate buyer interactions.
3. **Review Analysis & Summarization:**  
   - NLP to summarize and analyze customer reviews.
4. **Personalized Recommendations:**  
   - Collaborative filtering and content-based algorithms for buyer preferences.
5. **Dynamic Price Estimation:**  
   - XGBoost and regression models for accurate price predictions.

**Training and Evaluation Plan:**  
- **Data Collection:** From postings, queries, reviews, and market prices  
- **Preparation:** Handle missing fields, normalize, encode features  
- **Model Training & Evaluation:**  
  - Pricing: XGBoost/regression, evaluated via R², RMSE  
  - Chatbot/Assistant: Intent classification, evaluated for accuracy  
  - Review Summarization: Sentiment and insights extraction  
- **Deployment:** Models served as API via Flask, integrated with the React frontend

---

### **Data Management and Processing**

**Data Sources:**  
- APIs (vehicle info, showrooms, pricing, stock)  
- Datasets (historical prices, reviews, FAQs)

**Preprocessing Techniques:**  
- Handle missing values, normalize numeric and encode categorical data  
- Text pre-processing for NLP (chatbot, summarization)  
- Embedding generation for recommendations and FAQ retrieval

**Storage / Data Pipeline:**  
- **Database:** MongoDB for all core entities and AI metadata  
- **Pipeline:**  
  1. Data ingestion (APIs, batch upload)  
  2. Pre-processing, normalization, encoding, storage  
  3. AI model queries for predictions and recommendations  
  4. Frontend access via Flask API in real time

---

### **Implementation Plan**

**1. Initial Setup & Environment**  
- Set up React frontend, Flask backend, and MongoDB  
- CI/CD pipelines for deployment  
- Database schema design for all entities

**2. Core Module Development**  
- Vehicle browsing, filters, and sorting  
- Product pages & comparison  
- Finance tools (EMI, fuel calculator)  
- Used bike module  
- Showrooms & test rides (Google Maps integration)  
- **AI Modules:**  
  - Price prediction (XGBoost/regression)  
  - RAG chatbot  
  - AI calling companion  
  - Smart recommendations  
  - Review summarization

**3. Integration & Testing**  
- Frontend-backend integration  
- AI integration with backend APIs  
- Booking & notification systems (email/SMS)  
- Comprehensive unit, integration, and system testing

**4. Production-ready Build**  
- Frontend asset minification, backend query optimization  
- Auto-scaling and reliability measures  
- Performance monitoring for high uptime and speed

---

### **Evaluation and Validation**

**Assessment Indicators:**  
- **Price Estimation:** R², RMSE, MAE  
- **Chatbot & Voice Response:** Intent accuracy, query resolution rates  
- **Review Summarization:** ROUGE, BLEU scores  
- **System Metrics:** API response <1s, 99.9% availability

**Test Approach:**  
- **Unit Tests:** Search, filters, calculators, AI predictions  
- **Integration Testing:** Frontend-backend comms, DB, AI API  
- **System Testing:** Full flow (browsing, booking, AI, notifications)  
- **Load & Stress Testing:** Scalability, cache, CDN speeds  
- **User Acceptance Testing:** Dealer/user feedback, usability, feature enhancement

---

### **Deployment & Scalability**

**Deployment:**  
- **Hosting:** Platforms like Heroku, Render, or AWS EC2  
- **Backend & Frontend:** Flask for backend, React for frontend (together or separate)  
- **Database:** MongoDB Atlas (cloud-hosted)  
- **AI Models:** Served via Flask APIs, pre-loaded for real-time inference  
- **Third-Party Services:**  
  - Google Maps API (showroom locations)  
  - Twilio (AI calling/digital assistant)  
  - SMTP/Email Services (notifications)

**Scalability Considerations:**  
- **Vertical Scaling:** Increase server capacity (CPU, RAM)
- **Database Optimization:** Use indexing for efficient queries
- **Caching Mechanisms:** Use in-memory caching (Python dict, Redis) for high-demand data
- **Modular Design:** Keep components loosely coupled for horizontal scaling
- **Future Expansion:** Easy integration of new AI models and vehicle categories

---
