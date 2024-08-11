## Overview
CogniEdu can be broken down into two process flows:
1. New Students: New students will complete an onboarding process to set up their profile with CogniEdu and integrate their accounts for information extraction. After this, they will be able to access their optimized calendar and converse with Ed.
2. Returning Students: Returning students do not need to undergo the onboarding process. Once they input their credentials, they will be able to view their optimized calendar and converse with Ed.

https://github.com/user-attachments/assets/7f5999bb-6809-43cd-9757-807c4d87f55f

---
### [Landing Page](https://github.com/Foroughmo/CogniEdu/blob/main/8_Streamlit/app.py) <a name="Landing-Page"></a>
  <p align="center">
  <img width="600" alt="Landing Page" src="https://github.com/Foroughmo/CogniEdu/blob/main/0_Documents/Assets/LandingPage.png">

The Landing Page directs new students to "Register Here" and returning students to "Log in Here."

---
### New Student Registration <a name="New-Student-Registration"></a>

##### [Register Here Page](https://github.com/Foroughmo/CogniEdu/blob/main/8_Streamlit/pages/1_Registration_Page.py) <a name="Register Here Page"></a>
  <p align="center">
  <img width="600" alt="Registration Page" src="https://github.com/Foroughmo/CogniEdu/blob/main/0_Documents/Assets/RegistrationPage.png">

New students are directed to input their email address, full name, and password to create a new account.

##### [Integration Page](https://github.com/Foroughmo/CogniEdu/blob/main/8_Streamlit/pages/2_Integration_Page.py) <a name="Integration-Page"></a>
  <p align="center">
  <img width="600" alt="Integration Page" src="https://github.com/Foroughmo/CogniEdu/blob/main/0_Documents/Assets/IntegrationPage.png">

Integration with external accounts are meant to occur in this page. New students integrate their Google Classroom and Google Calendar platforms.

##### Ed Says Hi! <a name="Ed-Says-Hi!"></a>
  <p align="center">
  <img width="600" alt="Ed Says Hi" src="https://github.com/Foroughmo/CogniEdu/blob/main/0_Documents/Assets/EdSaysHi.png">

New students are shown a pop up of Ed introducing himself as the personal AI Chatbot assistant.

##### [Questionnaire Page](https://github.com/Foroughmo/CogniEdu/blob/main/8_Streamlit/pages/3_Onboarding_Page.py) <a name="Questionnaire-Page"></a>
  <p align="center">
  <img width="600" alt="Onboarding Questionnaire" src="https://github.com/Foroughmo/CogniEdu/blob/main/0_Documents/Assets/OnboardingQuestionnaire.png">

Ed directs students to tailor their experience with CogniEdu! This is where students can provide their preferences, such as studying times, whether they are a morning person or not, preferred break times, etc.

---
### Returning Student Log-In <a name="Returning-Student Log-In"></a>

##### [Log-in Page](https://github.com/Foroughmo/CogniEdu/blob/main/8_Streamlit/pages/4_LogIn_Page.py) <a name="Log-in Page"></a>
  <p align="center">
  <img width="600" alt="Log In Page" src="https://github.com/Foroughmo/CogniEdu/blob/main/0_Documents/Assets/LogInPage.png">

Returning students are directed to input their email address and password to log back into their account.

##### Welcome Back! <a name="Welcome-Back!"></a>
  <p align="center">
  <img width="600" alt="Welcome Back" src="https://github.com/Foroughmo/CogniEdu/blob/main/0_Documents/Assets/WelcomeBack.png">

Returning students are shown a pop up welcoming them back to CogniEdu. 

---
### [Home Page](https://github.com/Foroughmo/CogniEdu/blob/main/8_Streamlit/pages/5_Home.py) <a name="Home-Page"></a>
  <p align="center">
  <img width="600" alt="Home Page" src="https://github.com/Foroughmo/CogniEdu/blob/main/0_Documents/Assets/HomePage.png">

The Home Page includes the optimized calendar, a dedicated section for Ed, the student's friendly AI chatbot, and a view of the upcoming events. 
* The calendar is set to a day view for focused viewing of the day's schedule with a red line and arrow indicating the current time.
* Upcoming events show the next 3 events, as well as relevant details pertaining to them.
* Ed is located below to direct the student to utilize his AI Chatbot assistance.*

### [Calendar Page](https://github.com/Foroughmo/CogniEdu/blob/main/8_Streamlit/pages/6_Calendar.py) <a name="Calendar-Page"></a> 
  <p align="center">
  <img width="600" alt="Calendar Page" src="https://github.com/Foroughmo/CogniEdu/blob/main/0_Documents/Assets/CalendarPage.png">

The Calendar Page is the student's dedicated space to view a full week's optimized schedule. The event colors represent their source:
* Light Blue: Student's Google Calendar Events
* Navy: Classes from Google Classroom
* Pink: Ed's Optimizer Events

### [Ed, AI Chatbot Page](https://github.com/Foroughmo/CogniEdu/blob/main/8_Streamlit/pages/7_Chatbot.py) <a name="Ed-AI-Chatbot-Page"></a> 
  <p align="center">
  <img width="600" alt="Chatbot Page" src="https://github.com/Foroughmo/CogniEdu/blob/main/0_Documents/Assets/ChatbotPage.png">

The Ed, AI Chatbot Page allows for conversation pertaining to the student's course materials and their calendar. Recommended questions are provided to assist the student in making queries to Ed.

### Email Notification <a name="Email-Notification"></a>
  <p align="center">
  <img width="285" alt="Email Notification" src="https://github.com/Foroughmo/CogniEdu/blob/main/0_Documents/Assets/EmailNotification.png">

An email notification is sent each time the student's optimized calendar is generated.
