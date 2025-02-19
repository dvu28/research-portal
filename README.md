# System Design for a Research Portal

## System Overview

The portal will be built in React as the frontend and Node.js/Express server as the backend. It will also be divided into four different roles with its respective user experience and interactions. These roles will be: General Users, Scientists, Owners, and Stakeholders. 

**Users:** Allows users to search and view datasets, interact with notebooks, access code repos, and other publications.
- Their interaction includes, browsing, searching, using the interactive notebook, and viewing content 

**Scientists:** Allows scientists to upload, update, and manage materials through secure roles. 
- A dashboard dedicated for them to upload and manage their materials, which turns into metadata for database purposes 
- Their interaction includes managing their materials from submitting to viewing their submission status and interacting with the notebooks

**Owners:** Allows owners to management content, update UI, and approve scientist interactions such as submitting materials.
- Their interaction includes admin level managment of the portal with a dedicated dashboard 

**Stakeholders:** Dedicated dashboard that highlights funded projects, displays impact metrics (via charts and graphs), and showcases key contributor. 
- Their interaction includes viewing detailed reports or data of a research

![my image](https://github.com/dvu28/research-portal/blob/d567a3b93b8e6f46c8e2f74d2658a48f95ea2411/research%20portal%20diagram.png)

## Technology Choices

**Front-End:**
The frontend with React will be responsible for taking user interactions of the portal and communicate that with the backend through the Express server with APIs. <br>
<br>
<ins>React.js (Javascript Framework):</ins>
- Lightweight framework used to build user interface
- Leverages React Routers, which will set up client-side navigation for users to interact and navigate through screens of the portal

**Back-End:** 
The backend takes the users interaction and does certain operations depending on how each kind of roles interact with the portal. This also includes CRUD operations: Create, Read, Update, and Delete. Integration of API's play a huge part as it is the instructions of how the portal will work. The server will be repsonsible for operations such as security, uploaded/downloaded materials, launching notebook sessions, CRUD and serving specific data for stakeholders. <br>
<br>
<ins>Node.js with Express Server:</ins>
- Used to build RESTful APIs, which is the Express API gateway
- This sets up API endpoints to handle each role's interaction such as sending GET request
- Example is when a user wants to view a publication, they are sending a GET request to the Express server to retrieve the publication
- Every interaction with the portal by each role goes through the API layer

<ins>AWS S3:</ins>
- Stores larger files like datasets, publications and code repos
- A S3 bucket will enable proper access policies
- Integrated with the backend

<ins>PostgreSQL:</ins>
- Stores structured data such as user profiles, material submissions, etc.
- The backend communicates with the database for CRUD operations
- Example is when a scientist uploads new material, they use a POST request, and the database performs a Create operation, which ultimately creates data associated to that uploaded material

<ins>JupyterHub:</ins>
- The Express server can also provide an API endpoint to launch interactive notbook sessions
- Example would be if a user wants to launch a notebook session, they are essentially making a GET request to the backend so that the user can retrieve the notebook session

## Timeline & Resources

8‑Week Timeline & Resources
<ins>Week 1-2: Requirements, Design and Planning:</ins>
- Product Manager: Meet stakeholder and possible representives to discuss needs/goals, establish Aglie/Scrum/SDLC, and floats around entire project
- System Architect and Lead Engineer: Develop system design and finalize tech stack
- UI/UX Designer: Ideate wireframes and design

<ins>Week 2-3: Environment Setup and Project Kickoff:</ins>
- DevOps Engineer: Configure CI/CD, local environments, and basic infrastructure.
- Backend and Frontend Engineers: Begin familiarization with the project structure and initial development tools/environment
- System Architect: Oversee integration of the system design with technical setup from DevOps
- UI/UX Designer: Finalize UI Design and prototype

<ins>Week 3-5: Concurrent Backend & Frontend Development:</ins>
- Backend Engineers: Focus on APIs, Express server, authentication, and all service integrations
- Frontend Engineers: Focus on all UI components for each of the roles
- UI/UX Designer: Hand off work and provide continuous design refinements if needed


<ins>Week 6: Integration and Initial Testing:</ins>
- Frontend and Backend Engineer: Integrate API endpoints with the React application
- UI/UX Designer: Iterate on design based on user interactions and feedback
- DevOps Engineer: Validate that role-based access and data flows meet security standards 

<ins>Week 7: Comprehensive Testing & Quality Assurance:</ins>
- QA Team: Run automated and manual tests and report bugs
- Frontend and Backend Engineers: Address issues as they arise
- Stakeholder Reps: Provide feedback on usability and validate that the portal meets requirements with possible early users

<ins>Week 8: Deployment, Launch, and Post-Launch Preparation:</ins>
- DevOps Engineer: Handle containerization, production environment setup, and deploy portal to production
- Frontend and Backend Engineers: Provide final adjustments and ensure a smooth rollout
- Project Manager: Oversee the launch process and coordinate post-launch support
- Support Team: Ready to monitor and resolve issues after launch

## Risk Assessment

Two crucial risk that would impact the project the most would be security and development delays.

<ins>Security Risk:</ins>
- The nature of the project requires robust authentication system
- Data is at risk especially if data is sensitive from researches
- Unauthorize access can lead to open ended risks

<ins>Security Mitigation:</ins>
- Regular security measurements such as code reviews, vulnerability assessments, or even pen testing
- Implement security measurements such as JWT Auth
- Encryption for all data in transit 

<ins>Developemt Delay Risk:</ins>
- Unforseeable challenegs can always arise
- Combined roles can lead to work overload

<ins>Development Delay Mitigation:</ins>
- Agile methodology with recurring sprint meetings will allow the team to address those challanges and always be aligned with the progress
- Divide up the roles by utilizing more specialized roles