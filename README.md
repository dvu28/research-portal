# System Design for a Research Portal

## Designing the System

### System Overview

The portal will be built in React as the frontend and Node.js/Express server as the backend. The portal will also be divided into four different roles with its respective user experience and interactions. These roles will be: General Users, Scientists, Owners, and Stakeholders. 

Users: Allows users to search and view datasets, interact with notebooks, access code repos, and other publications. <br>
- A generic user dashboard 
Scientists: Allows scientists to upload, update, and manage materials through secure roles. <br>
- A dashboard dedicated for them to upload and manage their materials
Owners: Allows owners to management content, update UI, and approve scientist interactions such as submitting materials. <br>
- An admin dashbaord to manage the portal
Stakeholders: Dedicated dashboard that highlights funded projects, displays impact metrics (via charts and graphs), and showcases key contributor. <br>
- asdfadfa

insert diagram

### Technology Choices
**Front-End:**
The frontend with React will be responsible for taking user interactions of the portal and communicate that with the backend through the Express server with APIs. <br>
Technologies: React <br>
<ins>React.js (Javascript Framework)</ins>
- Lightweight framework used to build user interface
- Leverages React Routers, which will set up client-side navigation for users to interact with the portal

**Back-End:** 
The backend takes the users interaction and does certain operations depending on how each kind of roles interact with the portal. <br>
Technologies: Node.js, Express Server, AWS S3, PostgreSQL, JupyterHub <br>
<ins>Node.js with Express Server:</ins>
- Used to build RESTful APIs, which is the Express API gateway
- This sets up API endpoints to handle each role's interaction such as sending GET request to retrieve publications when a user searches
- Every interaction with the portal by each role goes through the API layer

<ins>AWS S3:</ins>
- Stores larger files like datasets, publications and code repos
- A S3 bucket will enable proper access policies
- Integrated with the backend

<ins>PostgreSQL:</ins>
- Stores structured data such as user profiles, material submissions, etc.
- The backend communicates with the database for CRUD operations
