<h1 align="center"> CogniEdu: AI-Powered Academic Planning for Student Success </h1>

<p align="center">
<img width="300" alt="CogniEdu Logo" src="0_Documents/Assets/CogniEduLogo.png">
</p>

CogniEdu is an academic planning tool designed to help students effectively manage their academic schedules alongside other commitments.

# **📑 Table of Contents**

1. [Project Motivation](#Project-Motivation)

2. [Overview of CogniEdu](#Overview)
   * [Project Diagram](#Project-Diagram)  
   * [Front-End](#Front-End)  

3. [Project Components](#Project-Components) 
   * [Onboarding Experience](#Onboarding-Experience)      
   * [Database Management with SQL](#Database)
   * [Time Estimations by LLM for Optimizer Algorithm](#Time)   
   * [Optimizing Student’s Study Time with Heuristic Algorithm and Gemini](#Optimizing)
   * [Ed: Our Conversational AI RAG Application Utilizing Langraph](#Ed) 
   * [Proactive Alerts for On Task Management](#Notifications)
      
4. [Implementation Evaluation](#Implementation-Evaluation)
   * [Model Selection](https://github.com/Foroughmo/CogniEdu/tree/main/6_Model_Selection)
   * [Model Evaluation](https://github.com/Foroughmo/CogniEdu/tree/main/7_Model_Evaluation)

6. [Streamlit Built User Interface](#Streamlit)
   * [CogniEdu App Overview](#CogniEdu-App-Overview)
   * [Detailed Overview of CogniEdu](https://github.com/Foroughmo/CogniEdu/blob/main/8_Streamlit/App_Overview/app.md)
   
7. [Technical Challenges](#Technical-Challenges)

8. [CogniEdu's Market Presence and Opportunities](#Market-Presence-and-Opportunities)

9. [Future Works](#Future-Works)
   * [Possibilities with CogniEdu](#Possibilities-with-CogniEdu)
   * [Next Steps Timeline](#Next-Steps)

10. [Conclusion](#Conclusion)
    
11. [Tools Utilized](#Tools-Utilized)

12. [Reference](#Reference)

13. [Acknowledgements/About Us](#Acknowledgements)

> Repository Structure: [Click Here](0_Documents/Respository_Structure.md)

# **🎯 Project Motivation** <a name="Project-Motivation"></a>
<p align="center">
<img width="380" alt="Nick Ramen 1" src="0_Documents/Assets/NickRamen1.png">
</p>
The story begins with a hypothetical student, Nick Ramen. Nick, a college student, faces a common challenge: balancing the best college experience possible while maintaining good grades, a healthy sleep schedule, and a social life. However, he eventually overcommits and becomes overwhelmed, leading to a decline in grades and confusion on how to navigate his academic struggles.


<br> Like Nick, approximately 86% of college students face challenges in effectively managing their time, which can lead to procrastination, stress, and a decline in academic performance.<sup>[1](#footnote1)</sup>

**Here is how CogniEdu can help:**

CogniEdu simplifies the planning process by creating an optimized schedule tailored to the student’s preferences, skills, and commitments. With CogniEdu, students benefit from a dedicated AI Chatbot Assistant named Ed. Ed assists with organizing tasks, sending email reminders, answering questions about the calendar and classes, and supporting students in achieving academic success.


# **🧠  Overview of CogniEdu** <a name="Overview"></a>

### Project Diagram <a name="Project-Diagram"></a>
<img width="785" alt="Process Flow" src="0_Documents/Assets/ProcessFlow.png">

### Front-End <a name="Front-End"></a>
<img width="785" alt="Front-End" src="0_Documents/Assets/Front-End.png">


# 🧩 Project Components <a name="Project-Components"></a>

### 📋 Onboarding Experience <a name="Onboarding-Experience"></a>
Each student undergoes an onboarding experience that integrates their calendar and academic platform through API calls. During this process, users complete an onboarding questionnaire that Ed uses to learn about their study habits and academic preferences. This information allows Ed to personalize the planning experience according to each student’s needs. 

<h5 align="center"> Onboarding </h5>
<p align="center">
<img width="485" alt="Onboarding" src="0_Documents/Assets/Onboarding.png">
</p>

### [🗄️ Database Management with SQL](https://github.com/Foroughmo/CogniEdu/tree/main/1_SQL_Database) <a name="Database"></a> 
Upon user signup, the onboarding questionnaire populates the `User` table in MySQL. By integrating with the student's Google account, the application continuously syncs their Google Calendar event data with the MySQL database. 

<h5 align="center"> Calendar Sync Overview </h5>
<p align="center">
<img width="400" alt="Calendar Sync Overview" src="0_Documents/Assets/CalendarSyncOverview.png">
</p> 

The calendar sync involves an initial import of the student's full calendar, while the continuous sync regularly updates every X number of minutes. The sync also stores events and handles NEW, UPDATED, and DELETED items, per a logic. 

<h5 align="center"> Calendar Sync Logic </h5>

<p align="center">
<img width="400" alt="Calendar Sync Logic" src="0_Documents/Assets/CalendarSync.png">
</p> 

The MySQL database also houses assignment information, such as due dates and instructions, which is extracted from Google Classroom, and then transformed, before being loaded into said database. The RAG (Retrieval-Augmented Generation) application then leverages this comprehensive data set to provide personalized and optimized solutions.                                                
### [🕛 Time Estimations by LLM for Optimizer Algorithm](https://github.com/Foroughmo/CogniEdu/tree/main/2_LLM_Time_Estimation) <a name="Time"></a> 

The time estimation algorithm serves as the preliminary phase in preparing data for the optimizer. This process is executed in two steps utilizing Large Language Models (LLMs) through prompt engineering.

**Step 1: Assignment Difficulty Level**
The LLM evaluates the difficulty level of each assignment based on its content. Assignments are then categorized on a scale of easy, medium, or hard. These qualitative scales are converted into numerical values and stored accordingly.

**Step 2: Time Estimation**
Based on the assignment's content and its assigned difficulty level, the LLM estimates the time required to complete the assignment. Once the time estimation is determined, it is provided to the optimizer to create an optimized study plan.

<h5 align="center"> Time Estimation LLM </h5>
<p align="center">
<img width="700" alt="Time Estimation LLM" src="0_Documents/Assets/TimeEstimationLLM.png">
</p> 

### [🗓️ Optimized Scheduling via Heuristics and LLM Prompting](https://github.com/Foroughmo/CogniEdu/tree/main/3_Optimizer) <a name="Optimizing"></a> 
Leveraging Gemini’s advanced reasoning capabilities, our application generates a study schedule based on specified study durations (e.g., 2 hours, 4 hours). These durations are processed through a greedy heuristic optimization algorithm, which considers the student's availability and preferences. The algorithm strategically places these study sessions at optimal times throughout the day. The outcome is a comprehensive schedule that seamlessly integrates the student’s personal events with the newly optimized study times.

<h5 align="center"> Optimizer Algorithm </h5>
<p align="center">
<img width="700" alt="Optimizer" src="0_Documents/Assets/Optimizer.png">
</p> 
                                           
### [💬 Ed: Our Conversational AI Agent](https://github.com/Foroughmo/CogniEdu/tree/main/4_Chatbot) <a name="Ed"></a> 
CogniEdu's chatbot, Ed, is built on the ReAct (Reasoning and Acting) paradigm, leveraging LangGraph to create a dynamic, multi-tool agent. The system employs three key capabilities:

1. PDF Retrieval-Augmented Generation (RAG): This tool accesses and queries students' Google Classroom materials, providing efficient and relevant information from course documents.

2. Calendar Interaction: A dedicated tool enables conversational access to the student's personal and academic calendar, allowing for schedule queries and management.

3. Web Search Integration: Utilizing Tavily, the agent can fetch external resources to supplement course materials and provide additional learning support.

<h5 align="center"> ReAct Framework </h5>
<p align="center">
<img width="267" alt="ReAct Framework" src="0_Documents/Assets/ReActFramework.png">
</p> 

Ed processes user queries through an iterative cycle of reasoning (using a Large Language Model) and acting (employing these specialized tools). This ReAct architecture allows the agent to break down complex queries, determine the most appropriate tools to use, and synthesize information from multiple sources. By integrating these functionalities, students can seamlessly query their course resources, manage their schedules, and access relevant external content through natural language conversations. Ed also has the capability to answer follow up questions from the student by determining if the query is a follow up or not. The LangGraph framework enables Ed to maintain context and make informed decisions throughout these interactions, enhancing the overall user experience and academic support.

<h5 align="center"> Ed's Pipeline </h5>
<p align="center">
<img width="700" alt="Ed's Pipeline" src="0_Documents/Assets/EdPipeline.png">
</p> 

### [🔔 Proactive Alerts for On Task Management](https://github.com/Foroughmo/CogniEdu/tree/main/5_Email_Notification) <a name="Notifications"></a> 
Managing one's schedule effectively can often prove to be challenging. Ed sends email notifications with optimized calendar information to help users stay on track by extracting calendar data, formatting it into informative emails, and automating the process. Emails are securely sent by integrating with external email servers via Simple Mail Transfer Protocol (SMTP) and Secure Sockets Layer (SSL) for safe message transmission.

<p align="center">
<img width="200" alt="Ed" src="0_Documents/Assets/Ed.png">
</p> 

# 📊  Implementation Evaluation <a name="Implementation-Evaluation"></a>                                             
In selection of the model powering Ed, two models were compared, two of Google's Large Language Models were compared, Gemini 1.5 Pro and Gemini 1.5 Flash, using LangChain and AI​. Once Gemini 1.5 Flash was selected, its performance was further evaluated.

<img width="850" alt="Model Evaluation Dashboard" src="0_Documents/Assets/ModelEvaluation.png">

> Model Selection: [Click Here](https://github.com/Foroughmo/CogniEdu/tree/main/6_Model_Selection)

> Model Evaluation: [Click Here](https://github.com/Foroughmo/CogniEdu/tree/main/7_Model_Evaluation)

# [📱 Streamlit Built User Interface](https://github.com/Foroughmo/CogniEdu/tree/main/8_Streamlit) <a name="Streamlit"></a>                                             
CogniEdu utilizes Streamlit alongside custom CSS to develop an intuitive user interface, ensuring a cohesive user experience. The development involved leveraging Cloud Run and NGROK to facilitate seamless deployment and testing of the application in a scalable and secure environment.

https://github.com/user-attachments/assets/7f5999bb-6809-43cd-9757-807c4d87f55f

---

### [CogniEdu App Overview](https://github.com/Foroughmo/CogniEdu/blob/main/8_Streamlit/App_Overview/app.md) <a name="CogniEdu-App-Overview"></a>

CogniEdu can be broken down into two process flows:

1. New Students: New students will complete an onboarding process to set up their profile with CogniEdu and integrate their accounts for information extraction. After this, they will be able to access their optimized calendar and converse with Ed.
2. Returning Students: Returning students do not need to undergo the onboarding process. Once they input their credentials, they will be able to view their optimized calendar and converse with Ed.
   
> Detailed Overview of CogniEdu: [Click Here](https://github.com/Foroughmo/CogniEdu/blob/main/8_Streamlit/App_Overview/app.md)

### Home Page <a name="Home-Page"></a>
  <p align="center">
  <img width="600" alt="Home Page" src="0_Documents/Assets/HomePage.png">

The Home Page includes the optimized calendar, a dedicated section for Ed, the student's friendly AI chatbot, and a view of the upcoming events. 
* The calendar is set to a day view for focused viewing of the day's schedule with a red line and arrow indicating the current time.
* Upcoming events show the next 3 events, as well as relevant details pertaining to them.
* Ed is located below to direct the student to utilize his AI Chatbot assistance.*

### Calendar Page <a name="Calendar-Page"></a> 
  <p align="center">
  <img width="600" alt="Calendar Page" src="0_Documents/Assets/CalendarPage.png">

The Calendar Page is the student's dedicated space to view a full week's optimized schedule. The event colors represent their source:
* Light Blue: Student's Google Calendar Events
* Navy: Classes from Google Classroom
* Pink: Ed's Optimizer Events

### Ed, AI Chatbot Page <a name="Ed-AI-Chatbot-Page"></a> 
  <p align="center">
  <img width="600" alt="Chatbot Page" src="0_Documents/Assets/ChatbotPage.png">

The Ed, AI Chatbot Page allows for conversation pertaining to the student's course materials and their calendar. Recommended questions are provided to assist the student in making queries to Ed.

# **🤔 Technical Challenges** <a name="Technical-Challenges"></a>
1. **AI Hallucinations:** AI Systems Can Produce Hallucinations, Generating Misleading or Incorrect Information
2. **Privacy Concerns:** Students Provide Student Data that Need Safeguarding
3. **Limited Training Data:** Generative AI Created Synthetic Data Used Given Limited Data from Relying on Student Dataa ​
4. **Agentic System Run Time:** Increasing Complexity Affects Run Time
5. **Agentic System Tool Selection:** Implementing the Correct Logic for the Agent to Choose the Right Tool Based on Context​
6. **LLM Inconsistency:** LLM Responses Can Be Random or Inconsistent


# **🤝🏻 CogniEdu's Market Presence and Opportunities** <a name="Market-Presence-and-Opportunities"></a>
CogniEdu addresses a significant market need for academic planning and organization tools that integrate seamlessly with existing technologies like Google Calendar and Google Classroom. With the increasing complexity of student schedules and the growing reliance on digital academic tools, CogniEdu is well-positioned in the educational technology market. The platform aims to enhance and expand by collaborating with academic institutions and universities and by extending integration to other popular platforms like Outlook Calendar and Canvas, making CogniEdu a pre-installed feature for ease of access for students.


# 🚀 Future Works <a name="Future-Works"></a>  

### Possibilities with CogniEdu <a name="Possibilities-with-CogniEdu"></a>

1. **Feedback Loop:** To Track Student’s Progress and Success of CogniEdu Recommendations​
2. **Improving LLMs:** With the Permission of Students, Their Data Can Be Used for the LLMs to Return Smarter, User-Specific Responses​
3. **Partnerships:** Partner With Teachers, Parents, and Universities to Help Students on a Broader Scale​
4. **Robust Time Estimation:** More Robust Time Estimation Algorithm for Optimizer​
5. **Scale Features:** Each Component Can Be Scaled to Accommodate More Students and Plan for Longer Time-Periods​​ 

### Next Steps Timeline <a name="Next-Steps"></a>
<img width="650" alt="Next Steps" src="0_Documents/Assets/NextSteps.png">

# 🔚 Conclusion <a name="Conclusion"></a>
<p align="center">
<img width="380" alt="Nick Ramen 2" src="0_Documents/Assets/NickRamen2.png">
</p>

Now that Nick is equipped with CogniEdu, he is able to integrate all his educational platforms, follow Ed's tailored study plans, and organize his course materials. Slowly but surely, Nick has become a happier college student, able to manage all his commitments and become more organized and motivated than ever as his academic performance improves.

Now it's time to give CogniEdu a chance!

# **🛠️ Tools Utilized** <a name="Tools-Utilized"></a>

|  | Category | Tool(s) |
|----------|----------|----------|
| 1 | Data Visualization | ![Power Bi](https://img.shields.io/badge/power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black) |
| 2 | Database Management | ![MySQL](https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white) | 
| 3 | Design | ![Canva](https://img.shields.io/badge/Canva-%2300C4CC.svg?style=for-the-badge&logo=Canva&logoColor=white) ![Figma](https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white) <img width="97" alt="Screenshot 2024-08-06 at 2 21 06 PM" src="https://github.com/user-attachments/assets/28e7d4cc-db4b-4016-bc78-a7c73aa13f42"> <img width="85" alt="Screenshot 2024-08-06 at 2 34 32 PM" src="https://github.com/user-attachments/assets/fa685bf1-901c-4dec-b78c-a1afe60d2ecb">|
| 4 | Frameworks | ![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=Streamlit&logoColor=white) ![NGROK](https://img.shields.io/badge/ngrok-140648?style=for-the-badge&logo=Ngrok&logoColor=white) <img width="110" alt="Screenshot 2024-08-06 at 2 29 58 PM" src="https://github.com/user-attachments/assets/3d76bfd5-84a6-482f-ba87-4c87ef0923b7"> |
| 5 | IDEs | ![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white) | 
| 6 | Languages | ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) <img width="76" alt="Screenshot 2024-08-06 at 2 52 09 PM" src="https://github.com/user-attachments/assets/d24a382e-b3c9-4976-8b46-2d6d37e5718d">|
| 7 | Platforms | ![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white) |
| 8 | Project Management | ![Trello](https://img.shields.io/badge/Trello-%23026AA7.svg?style=for-the-badge&logo=Trello&logoColor=white) |

# 📚 Reference <a name="Reference"></a>
<a name="footnote1">1</a>: Gitnux. (n.d.). College student time management statistics. Retrieved from https://gitnux.org/college-student-time-management-statistics/

# 👤 Acknowledgements/About Us <a name="Acknowledgements"></a>                                                
  <p align="left">
  <img width="100" alt="ConvoCrafters Logo" src="0_Documents/Assets/ConvoCraftersLogo.png">

  Roselyn Rozario  ([@roselynrozario](https://github.com/roselynrozario))  
  Adela Cho  ([@Adelach0](https://github.com/Adelach0))  
  Michael Meissner  ([@mikemeissner1](https://github.com/mikemeissner1))  
  Forough Mofidi ([@Foroughmo](https://github.com/Foroughmo))  
  Joseph Strickland ([@JCStrick](https://github.com/JCStrick))

