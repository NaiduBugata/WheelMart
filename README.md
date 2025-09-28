**Project Title :** WheelMart

**Problem Statement Chosen :** Build a Two-Wheeler Marketplace Web App Given by Vahan Bazar

**Reason to Choose the Problem Statement:**
 We chose this Problem Statement because the two-wheeler market in India is one of the biggest and fastest-growing segments. However, the online buying and selling experience is still flawed. Buyers often need to visit multiple dealer websites, use finance calculators, and check review platforms. Dealers also find it hard to manage inventory, leads, and customer engagement.

**i) Proposed Approach:**
We will build the frontend using React to create a responsive user interface. We will integrate a Flask backend with a MongoDB database to manage listings, users, and dealers. Key modules will include search and filters, product details, comparisons, finance tools, and booking forms. 

**ii)Key Features / Modules:**

1.Display the picture, name, and cost of EVs, bikes, and scooters.

2. Search & Filters: Brand, price range, fuel type, mileage, and other criteria can be used to filter results.
   
3. Product Page: Offers extensive features, images, discounts, and prices.
   
4. Model Comparison: Side-by-side comparison of two or more vehicles.
   
5. Financial Tools: EMI and fuel cost calculators.
   
6. Used Bikes: Examine or offer for sale used bikes that have verified information.
    
7. Showrooms & Test Rides: A dealer directory and test ride reservation system.
    
8. AI chatbot: simple queries
    
9. Price Predictor: predicting fair bike prices for the seller

**c) System Architecture**
•	Architecture Diagram / Workflow

<img width="740" height="641" alt="image" src="https://github.com/user-attachments/assets/f56a790b-c2e6-494a-ba4c-a35be89acbcb" />
<img width="264" height="530" alt="image" src="https://github.com/user-attachments/assets/f886cfbc-5aa2-4047-9214-07f56fa824a5" />



**•	Data Flow Explanation**
1.Data flow starts with user interaction on the frontend. People browse bikes there. They apply filters or check out detailed product pages. All this happens through a React-based UI. Actions kick things off. Like comparing models. Or calculating EMI. Booking test rides too. Those trigger API requests right away.

2.Backend handles it from there. Using Flask mostly. It processes the requests. Applies business logic. Fetches data or updates stuff as needed. Take the EMI calculator for example. It uses the input values you put in. Comparison pulls up multiple bike specs. Booking form just stores user details in the system.

3.Database comes next. Stores all the data. Things like listings. Users. Dealers. Bookings. Reviews too. Could be relational or NoSQL setup. Queries get optimized. For fast search and filtering. Keeps everything running smooth.

4.External integrations tie in. Showroom maps run on Google Maps API. Payment gateways manage fees. For bookings or dealer subscriptions.

5.Finally responses go back to the UI. Processed data as JSON. Gets rendered into user-friendly interfaces.

**d) Technology Stack :**
**Frontend:**
	•React.js – For building a responsive and dynamic user interface.
	•Material UI / TailwindCSS/CSS – For styled components and modern UI design.
**Backend:**
	•Flask (Python) – Lightweight backend framework for handling APIs and business logic.
	•REST APIs – For communication between frontend and backend.
**Database:**
	•MongoDB – NoSQL database to store vehicle listings, users, dealers, bookings, and reviews.
**Machine Learning:**
	•Price Predictor – ML model to estimate used bike prices based on brand, age, mileage, and condition.
	•Libraries: Scikit-learn, Pandas, NumPy.
**AI Features:**
	•Chatbot Assistant – AI-powered bot to help users with browsing, comparisons, EMI queries, and recommendations.
	•Libraries/Services: OpenAI API / Rasa / Transformers (depending on integration).
**APIs & External Libraries:**
	•Google Maps API – Showroom locator & test ride directions.
	•Payment Gateway API – For booking fees or dealer subscriptions.
	•SMTP / Twilio API – For email/SMS notifications (test ride confirmations, price alerts).
	•Axios / Fetch – For API calls from frontend.
	•JWT Authentication – For secure user login and dealer dashboards.
**e) Algorithms & Models**
**i) Selected Algorithms and Justification**
1.	RAG-Powered Chatbot (Text & Web)
o	Role: A Retrieval-Augmented Generation framework that merges live data retrieval with deep language understanding to deliver precise and context-aware responses.
o	Application: Manages customer questions related to vehicle details, model comparisons, EMI calculations, upcoming releases, and general FAQs on the platform.
2.	AI Voice Assistant for Calls
o	Role: Utilizes Speech-to-Text (STT), Natural Language Processing for intent recognition, and Text-to-Speech (TTS) to automate interactions with buyers.
o	Application: Addresses common buyer inquiries such as pricing, availability, offers, and test ride scheduling—reducing manual workload for sellers while improving response speed.
3.	Review Analysis & Summarization
o	Role: NLP techniques scan large volumes of customer reviews, condensing them into meaningful insights and sentiment overviews.
o	Application: Enables buyers to quickly grasp collective feedback on vehicles and provides sellers with data-driven suggestions for service improvement.
4.	Personalized Recommendations
o	Role: Leverages a mix of collaborative filtering and content-based recommendation algorithms to predict individual preferences.
o	Application: Suggests best-fit vehicles, similar alternatives, and upgrade options based on browsing activity and user history.
5.	Dynamic Price Estimation
o	Role: Employs XGBoost and regression models to interpret factors such as market conditions, vehicle age, mileage, and demand trends for accurate price forecasts.
o	Application: Helps buyers identify fair value for used vehicles while supporting sellers in setting competitive prices.
**ii) Training and Evaluation Strategy**
1.	Data Acquisition: Collecting datasets from historical listings, user queries, customer reviews, and real-time market prices.
2.	Data Preparation: Managing missing fields, normalizing numerical inputs, encoding categorical data, and cleaning textual content.
3.	Model Training & Validation:
o	Pricing Models: Trained with XGBoost and regression; assessed using R² and RMSE metrics.
o	Chatbot & Call Assistant: Intent classification developed with Transformer/RNN models; validated for accuracy and response reliability.
o	Review Summarization: NLP pipelines designed to extract sentiments and key takeaways from review texts.
4.	Deployment: Models are deployed as APIs using a Flask backend, integrated seamlessly with the React frontend and connected voice platforms (e.g., Twilio).
**f) Data Handling **
**i) Data Sources:**
	•	APIs: Vehicle listings, showrooms, pricing data, and real-time inventory.
	•	Datasets: Historical two-wheeler sales, used bike prices, user reviews, and FAQs collected from public datasets and dealership records.

**ii) Preprocessing Methods:**
	•	Handle missing values, normalize numerical features (price, mileage, age).
	•	Encode categorical features (brand, fuel type, vehicle type).
	•	Clean and tokenize text data for NLP tasks (chatbot, review summarization).
	•	Generate embeddings for recommendations and FAQ retrieval.

**iii) Storage / Pipeline Setup:**
	•	Database: MongoDB for vehicles, users, dealers, bookings, reviews, and AI metadata.
	•	Pipeline:
	1.	Data Ingestion: API pulls & batch dataset uploads.
	2.	Preprocessing: Clean, normalize, encode, and store in MongoDB.
	3.	AI Models: Access preprocessed data for price prediction, recommendations, chatbot, and call assistant.
	4.	Frontend Access: Flask APIs serve processed data and AI predictions to React UI in real-time.

**g) Implementation Plan**

**1. Initial Setup & Environment**
	•	Infrastructure & Environment Setup: Configure React frontend, Flask backend, and MongoDB database for core operations.
	•	CI/CD Pipelines: Implement automated deployment pipelines to ensure smooth code integration and delivery.
	•	Database Schema Design: Define collections for users, dealers, vehicles, bookings, AI metadata, and review data.

**2. Core Module Development**
	•	Vehicle Browsing & Filters: Implement search, filter, and sort capabilities for bikes, scooters, and EVs.
	•	Product Pages & Comparison: Detailed specifications, images, and side-by-side comparison of multiple vehicles.
	•	Finance Tools: EMI and fuel cost calculators.
	•	Used Bike Module: View and sell pre-owned vehicles.
	•	Showrooms & Test Rides: Dealer directory, booking forms, and location integration with Google Maps API.
	•	AI Modules Development:
	•	Price Prediction: XGBoost and regression models for resale value estimation.
	•	RAG-Based Chatbot: Contextual, real-time answers to user queries.
	•	AI Calling Assistant: Automates repetitive seller-side calls using STT, NLP, and TTS.
	•	Smart Recommendations: Collaborative and content-based filtering for personalized suggestions.
	•	Review Summarization: NLP-based insights from user reviews.

**3. Integration & Testing**
	•	Frontend-Backend Integration: Connect React UI with Flask APIs for seamless data flow.
	•	AI Integration: Connect all AI modules (chatbot, call assistant, price predictor, recommendations, review summarization) to backend APIs for real-time access.
	•	Booking & Notification Systems: Integrate test ride booking, used bike sales, and notifications via email/SMS (Twilio).
	•	Comprehensive Testing: Unit tests, integration tests, and system tests to ensure performance, reliability, and accuracy of AI models and core functionalities.

**4. Final Deployment-ready Build**
	•	Optimization: Minify frontend assets, optimize backend queries, and ensure fast response times.
	•	Auto-Scaling: Enable horizontal scaling, read replicas, and asynchronous task queues to handle peak loads.
	•	Performance & Reliability: Maintain sub-second response times and 99.9% uptime, ensuring the platform is ready for millions of users and thousands of dealers.

**h) Performance and Validation**

**1. Evaluation Metrics**

**Price Prediction:**

Accuracy measured using R² score, RMSE, and MAE to validate resale value estimation.

**Chatbot & Voice Assistant:**

Intent classification accuracy ensures correct query understanding.

Response relevance and query resolution rate indicate overall effectiveness.

**Review Summarization:**

ROUGE and BLEU scores assess how well key insights and sentiments are extracted.

**System Performance:**

API response time targeted at <1 second.

Service uptime maintained at 99.9%.

**2. Testing Strategy**

**Unit Testing:**

Validates individual components such as search, filters, calculators, and AI predictions.

**Integration Testing:**

Ensures smooth interaction between frontend and backend.

Confirms proper database connectivity and AI API integration.

**System Testing:**

End-to-end validation of features like browsing, comparisons, booking, AI responses, and notifications.

**Load & Stress Testing:**

Simulates peak usage to check system scalability.

Verifies caching efficiency and CDN performance.

**User Acceptance Testing (UAT):**

Involves real users (e.g., dealers) to gather feedback.

Focuses on usability, feature improvements, and final adjustments before deployment.

**(i)Deployment & Scalability**

**Deployment**

**Hosting Platform:** Application can be deployed on beginner-friendly services such as Heroku, Render, or AWS EC2.

**Backend & Frontend:** Flask handles the backend while React powers the frontend; both can be hosted together or as separate services communicating through APIs.

Database: MongoDB is managed on MongoDB Atlas (cloud-hosted) for reliability and ease of access.

**AI Models:** Exposed as Flask APIs, with models preloaded during server startup to enable real-time inference.

**Third-Party Services:**

Google Maps API → showroom locations.

Twilio → AI-powered calling assistant.

SMTP/Email services → notifications and alerts.


**Scalability Considerations**
**Vertical Scaling:** Increase server resources (CPU, RAM) to accommodate higher traffic.

**Database Optimization:** Apply indexing and efficient query handling to manage large volumes of listings and user data.

**Caching Mechanism**: Use lightweight in-memory caching (e.g., Python dictionary, Redis in future) for high-demand data like vehicle listings and FAQs.

**Modular Design:** Keep frontend, backend, and AI components loosely coupled to enable horizontal scaling.

**Future Expansion: **Architecture supports adding new AI models, more vehicle categories, and growing user base without major redesign.

**Sample output:**

