# 🌐 MERN Application Containerization with Docker  

This project demonstrates the **containerization** of a full-stack MERN application (MongoDB, Express.js, React.js, Node.js) using **Docker**. 🚀  

## ✨ Key Highlights  

- 🛡️ **Custom Virtual Network**: Designed a secure **Docker virtual network** for isolated container communication.  
- 🧩 **Modular Containers**:  
  - 📦 **Frontend**: React.js app served via a dedicated container.  
  - 🖧 **Backend**: Node.js server running independently.  
  - 🗄️ **Database**: MongoDB container for seamless data management.  
- 🔗 **Container Communication**: Ensured smooth interaction between containers using **Docker Compose** with industry best practices.  
- 📊 **Scalability and Portability**: Simplified deployment and scaling of the entire stack in any environment.

## 🛠️ Technologies Used  

- **Docker** 🐳: For containerization of the MERN stack.  
- **Docker Compose** 📄: To define and manage multi-container deployment.  
- **MERN Stack**:  
  - React.js (Frontend)  
  - Node.js & Express.js (Backend)  
  - MongoDB (Database)  


### Create a network for the docker containers

`docker network create demo`

### Build the client 
```sh
cd mern/frontend
docker build -t mern-frontend .
```

### Run the client

`docker run --name=frontend --network=demo -d -p 5173:5173 mern-frontend`

### Verify the client is running

Open your browser and type `http://localhost:5173`

### Run the mongodb container

`docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongodb:latest`

### Build the server

```sh
cd mern/backend
docker build -t mern-backend .
```

### Run the server

`docker run --name=backend --network=demo -d -p 5050:5050 mern-backend`

## Using Docker Compose

`docker compose up -d`

## 🌟 Learnings
- Mastered Dockerfile and Docker Compose for multi-container deployment.
- Improved understanding of container networking and isolation.
- Gained hands-on experience with deploying scalable applications in a containerized environment.
