# System Design for a Research Portal

## System Overview

The portal will be built in React as the frontend and Node.js/Express server as the backend. The portal will also be divided into four different roles with its respective user experience and interactions. These roles will be: General Users, Scientists, Owners, and Stakeholders. 

**Users:** Allows users to search and view datasets, interact with notebooks, access code repos, and other publications.
- Their interaction includes, browsing, searching, using the interactive notebook, and viewing content 

**Scientists:** Allows scientists to upload, update, and manage materials through secure roles. 
- A dashboard dedicated for them to upload and manage their materials, which turns into metadata for database purposes 
- Their interaction includes managing their materials from submitting to viewing their submission status and interacting with the notebooks

**Owners:** Allows owners to management content, update UI, and approve scientist interactions such as submitting materials.
- Their interaction includes admin level managment of the portal with a dedicated dashboard 

**Stakeholders:** Dedicated dashboard that highlights funded projects, displays impact metrics (via charts and graphs), and showcases key contributor. 
- Their interaction includes viewing detailed reports or data of a research

insert diagram

## Technology Choices

**Front-End:**
The frontend with React will be responsible for taking user interactions of the portal and communicate that with the backend through the Express server with APIs. <br>
<br>
<ins>React.js (Javascript Framework)</ins>
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

