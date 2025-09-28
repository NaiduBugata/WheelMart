**Project Title :** WheelMart  
**a) Problem Statement Reference**
Chosen Problem Statement : Build a Two-Wheeler Marketplace Web App Given by Vahan Bazar  
Reason for Choosing Problem Statement:  
We chose this Problem Statement because the two-wheeler market is one of the largest and fastest-growing segments in India. However, the online buying and selling experience is still broken. Buyers usually have to visit many dealer websites, use finance calculators, and visit review platforms. Dealers are also struggling a lot to manage inventory, leads, and engagement.  

**b) Solution Overview**
i) Suggested Method:  
The frontend will be created with React for a responsive user interface. The backend will be created with Flask in connection with a MongoDB database for maintaining listing information, users, and dealers. Major modules will include: search and filters, product details, side-by-side comparisons, financial calculators, and booking forms.  

ii)Major Features / Modules:  
1. Present big photos, name, and price for the EVs, bikes, and scooters.  
2. Search & Filters: Allow results to be filtered, such as by brand, price, fuel type, mileage, etc.  
3. Product Page: Provide comprehensive features, pictures, discount rates, and prices for the product.  
4. Model Comparison: Provide side-by-side comparisons of two or more vehicles.  
5. Financial Tools: Calculate EMI and fuel costs.  
6. Used Bikes: Show or provide used bikes for sales that are verified.   
7. Showrooms & Test Rides: Provide a dealer list and schedule for test rides with dealers.  
8. AI chatbot: answer common queries  
9. Price Predictor: for predicting fair price for bike for seller  

**c) System Architecture**  
• Architecture Diagram / Workflow  

<img width="740" height="641" alt="Screenshot 2025-09-28 195702" src="https://github.com/user-attachments/assets/7cd8db84-0703-431c-9061-7d2ae03e5b64" />

<img width="264" height="530" alt="image" src="https://github.com/user-attachments/assets/f886cfbc-5aa2-4047-9214-07f56fa824a5" />  

• Explanation of Data Flow  
1.The data flow begins at the frontend where users navigate the bikes. They filter things and view product detail pages. All this is done through a React-based user interface. The actions – like model comparison, EMI calculations, or test ride booking – make the request even when doing those things.  
2.Since the request comes into the backend, we get engaged. PHP handles the backend mostly. This means the request gets processed, business logic is imposed, and maybe gathering information and updating information (for lack of a better word). Take the EMI calculator, for instance – the input values are used in the EMI calculation. The comparison gets several specs for each bike when queried, and the booking form just collects relevant user information on the backend in the system.  
3.Data is persisted next in the database. Relevant entities like listing as well as users, dealers, bookings, and reviews. This can be relational or noSQL persistence. It’s optimized for fast search and filtering to keep things running efficiently.  
4.External services make a commitment. The showroom maps are based on a Google maps API, and the fee collection payment gateways are for bookings and dealer subscriptions.  
5.Responses are processed at the UI as JSON data and rendered as user-friendly interfaces.  

**d) Technology Stack:**
Frontend:  
• React.js – To create a dynamic and responsive user interface.  
• Material UI / TailwindCSS / CSS – For styling and building modern UIs.  

Backend:  
• Flask (Python) – A lightweight backend fraemwork for APIs and business logic.  
• REST APIs – For communication between frontend and backend.  

Database:  
• MongoDB – NoSQL database to store vehicle listings and information about users, dealers, bookings and reviews.  

Machine Learning:  
• Price predictor – A simple ML model to predict the price of a used bike based on its brand, age, mileage, and condition.  
• Libraries: Scikit-learn, Pandas, NumPy.  

AI Features:  
• Chatbot Assistant – A bot powered by AI to help users browse bikes, perform bike comparisons, ask about EMI, and provide recommendations.  
• Libraries or Services: OpenAI API / Rasa / Transformers (for integration).  

APIs && External Libraries:  
• Google Maps API – For locating showrooms and getting directions for test rides.  
• Payment Gateway API – For booking fees or subscriptions for dealers.  
• SMTP / Twilio API – For notifications via email or SMS (test ride confirmations, when bikes drop in price).  
• Axios / Fetch – For making API calls from the frontend.  
• JWT Authentication – For secure logins and dealer dashboards.  

**e) Algorithms & Models**  
i) Selected Algorithms and Justification  
1. RAG-Powered Chatbot (Text & Web)  
o Function: A Retrieval-Augmented Generation framework that combines retrieval of live data with deep language comprehension to provide accurate, contextually relevant, and accountable responses.  
o Use Case: This bot will address consumers' questions in relation to vehicle specifications, model comparisons, EMI calculations, launches, and other relevant FAQs on the platform.  

2. AI Voice Assistant (Calls)  
o Function: Leverage Speech-to-Text (STT) speech recognition, Natural Language Processing to identify intent, and Text-to-Speech (TTS) for automation of interactions with buyers.  
o Use Case: This assistant will deal with common questions buyers ask such as the pricing, availability, offers, and scheduling test rides which will reduce emotional labor for sellers while providing faster responses.  

3. Review Analysis & Summarization  
o Function: Natural Language Processing techniques to read potentially hundreds of customer reviews and summarize them into relevant insights and an overview of the general sentiment.  
o Use Case: Will allow customers to quickly see what people think about the vehicle and potentially provide sellers with suggestions for improvement based on the feedback.  

4. Personalized Recommendations  
o Function: Uses a mix of collaborative filtering and content-based recommendation algorithms to learn and predict individual preferences.  
o Use Case: Werx can offer the best vehicle for a buyer's chosen specifications, highlight similar vehicle options, and offer upgrades options based on click behaviour and previous user's shareable data.  

5. Dynamic Price Estimation   
o Function: Utilizes XGBoost and regression models to examine features like market conditions, car's age, mileage, and trends related to demand for accurate price predictions.   
o Use: Allows buyers to know fair value for used cars while assisting sellers in pricing competitively.  

ii) Training and Evaluation Plan  
1. Data Collection: Compiling datasets from historical postings, user queries, customer reviews, and market prices on real time.   
2. Data Preparation: Reviewing missing fields, normalizing numerical values, encoding categorical features, and reviewing text data.   
3. Model training & evaluation:   
o Pricing Models: Trained using XGBoost and regression and evaluated using R² and RMSE.   
o Chatbot & Call Assistant: Intent classification training using Transformer/RNN models and evaluated for accuracy and reliability in responses.   
o Review Summarization: NLP pipelines built with output being sentiment and key take aways from the review text   
4. Deployment: Models will be deployed as an API using a Flask backend integrated with the React frontend and connected to voice platforms (ie. Twilio).  

**f) Data Handling**
1) Data Sources:  
• APIs: for vehicle information, showrooms, pricing information and real-time stock information.   
• Data Sets: historical two-wheeler pricing statistics, used bike pricing, user reviews of used bikes and frequently asked questions, which have been compiled from publicly available data sets and information derived from the dealership's records.    

2) Preprocessing Techniques and Methods:  
• Handle cases of missing values, then normalize numeric values (price, mileage, age) and to encode categorical values (brand, fuel type, type of vehicle).    
• Manipulate and prepare text data for pre-processing involving natural language e.g. a chatbot or review summarization.    
• Create embedding for natural language processing involving recommendations and retrieval of FAQs.   

3) Storage / Setup for Data Pipeline:  
• Database: MongoDB for storing vehicle, user, dealer, booking for users, reviews and to capture metadata in AI processing.  
• Pipeline:   
1. Data ingestion: taking API pulls & facilitated batch-uploading of data set files.   
2. Pre-processing: clean, normalize, encode, and store in MongoDB; using middleware to connect react web app.  
3. AI models: query pre-processed data on the database for price prediction, recommendations, chatbot and agent on phone assistant.  
4. Front end access: via a Flask API, as requests are made when queries are made they will be served with information from DB alongside predictions - to be displayed through React UI, in real time.  

**g)Implementation Plan**

1. Initial Setup & Environment  
• Infrastructure & Environment Setup: Set up and configure the React front-end, Flask back-end, and MongoDB database to support core application functionality.   
• CI/CD Pipelines: Set up automated deployment pipelines to facilitate pull requests and to get code to production efficiently and reliably.  
• Database Schema Design: Identify collections for users, dealers, vehicles, bookings, AI metadata, and review data.  

2. Core Module Development  
• Vehicle Browsing & Filters: Develop vehicle search, filter, and sorting capabilities for bicycles, scooters, and electric vehicles.   
• Product Pages & Comparison: Vehicle specifications, photos, and side by side comparisons of multiple vehicles.   
• Finance Tools: EMIs, fuel cost calculators.   
• Used Bike Module: View and sell second-hand vehicles.   
• Showrooms & Test Rides: Showroom directory, booking forms, and integration of Google Maps API for locations.   
• AI Modules Development:  
• Price Prediction: XGBoost and regression models for resale value prediction.   
• RAG Based Chatbot: Real time responses to contextual questions.   
• AI Calling Companion: Automate repetitive calls to sellers, STT, NLP, TTS.   
• Smart Recommendations: Collaborative filtering and content based recommendations to personalize suggestions.   
• Review Summarization: NLP generated insights based on user reviews.  

3. Integration & Testing  
• Frontend-Backend Integration: Link the React user interface with the Flask APIs to allow for seamless data to flow back and forth.  
• AI Integration: Connect the various AI modules (chatbot, call-assistant, price prediction, recommendations, review summarization) to the backend APIs to allow real-time access.  
• Booking & Notification Systems: Integrate test ride booking, used bike sales and notifications sent through email and/or SMS (twilio).  
• Comprehensive Testing: Unit tests, integration tests and system tests to evaluate performance, reliability, and accuracy of AI models and core functionalities.  

4. Production-ready Build  
• Optimization: Minify frontend assets, optimize backend queries, and run tests to make sure the system has fast response times.  
• Auto Scaling: Enable horizontal scaling, read replicas, and asynchronous task queues to handle unexpected loads.  
• Performance and Reliability: Maintain sub-second response times and 99.9% uptime to ensure the platform is ready for millions of users as well as thousands of dealers.  

**h)Performance & Validation** 
1. Assessment Indicators  
Price Estimation:  
Efficacy determined through R² score, RMSE, and MAE to confirm resale value approximation.  
Chatbot & Voice Response:  
Intent recognition accuracy guarantees the question is analyzed accurately.  
Referencing goal relevancy and query resolution rates indicates overall effectiveness.  
Review Summarization:  
ROUGE and BLEU to clarify if key insights and sentiment are derived.  
System Metrics:  
API to respond within <1 seconds.  
Service level availability at 99.9%.  

2. Test Approach  
Unit Tests:  
Validates single components such as search, filters, calculators, and AI predictions.  
Integration Testing:  
Verifies successful communication between the front and back end.  
Tests for successful database connection and AI API.  
System Testing:  
Complete testing to validate features such as browsing, comparisons, booking, AI activity, and notifications.  
Load & Stress Testing:  
Ability to mimic peak usage, to help evaluate system scalability.  
Evaluates cache performance and CDN access speeds.  
User Acceptance Testing (UAT):  
Engagement of actual users (e.g., dealers) to collect comments.  
Looks at usability, added features, and refinements leading up to production.  

**i)Deployment & Scalability** 
Deployment  
Hosting Platform: This Application’s hosting should be on a user-friendly application like Heroku, Render, or AWS EC2.  
Backend & Frontend: The backend is handled by Flask, while React provides the frontend; front-end and back-end can either both be hosted, or as separate services with back-end communicating through APIs.  
The database is MongoDB, hosted on the cloud with MongoDB Atlas to efficiently provide reliability and access.  
AI Models: Models are served as Flask APIs and with models pre-loaded during server startup, provides real-time inference.  
Third-Party Services:  
Google Maps API → showroom locations.  
Twilio → AI calling and digital assistant.  
SMTP/Email Services → notifications and alerts.  

**Scalability Considerations** 
*Vertical Scaling*: Increase server capacity (CPU, RAM) to support increased user activity.  

*Database Optimization:* Use indexation & other tactics to more effectively handle large numbers of listing data and user data via database queries.  

*Caching Mechanism* : Implement lightweight in-memory caching(e.g., motivational Python dictionary, Redis at a future point) for highly demanded data such as vehicle listings and FAQs.  

*Modular Design:* Keep the front-end, back-end, machine learning algorithms, and non-modern components (backend service) loosely coupled to allow the system to be horizontally scaled.  

*Future Expansion:*: Architecturally, any expansion such as adding new AI models and product vehicle in new categories to suit growing user numbers does not require an extensive redesign.
