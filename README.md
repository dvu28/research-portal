# System Design for a Research Portal

## Designing the System

**Front End**
Technologies: React

The portal will be divided into four different user experiences with it's own dashboard since there will be different kinds of roles interacting with the portal: General Users, Scientist, Owner, and Stakeholder.

React will be used to build out the user interface and will leverage React Routers, which will set up client-side navigation. This is how all four different users will be able to interact with the portal

Our frontend using React will be essentially responsible for taking user interaction of the portal and communicate with the backend with Express API via RESTful endpoints.

User Dashboard: Allows users to search and view, datasets, interact with notebooks, access code repos, and other publications.
Scientist Dashboard: Allows scientists to upload, update, and manage materials.
Owner Dashboard: Allows owners to management content, update UI, and approve submitted research.
Stakeholder Dashboard: Dedicated section that highlights funded projects, displays impact metrics (via charts and graphs), and showcases key contributor.

**Back End**
Technologies: Node.js, Express Server, AWS S3, PostgreSQL, JupyterHub

The backend will be set up with these specific technologies to handle creating, reading, updating, and deleting resources such as publications, user profiles, and research submissions...also known as CRUD operations. 

This will also utilize API endpoints
