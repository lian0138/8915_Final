# Full-Stack Cloud-Native Development  
## Lab Project Assignment: Building a Cloud-Native App for Best Buy

## **Scenario**  
Congratulations! You have been hired as a **Full-Stack Cloud-Native Developer** at Best Buy, a leading electronics retailer. Your manager has assigned you a project to develop a demo **cloud-native application** for Best Buy's online store.  

The application architecture must follow the design principles of the **Algonquin Pet Store (On Steroids)**, but with one key change:  
- **Order Queue Service** must be implemented as a managed backing service (e.g., Azure Service Bus) rather than an owned service like RabbitMQ.  

You will design, build, and deploy this application in a Kubernetes cluster and demonstrate its functionality.

---

## **Assignment Objectives**  
- Implement a cloud-native application using microservices architecture.   
- Develop and deploy a full-stack solution for Best Buy using Kubernetes.  
- Enable AI-powered product descriptions and image generation using GPT-4 and DALL-E.  
---

## **Application Overview**  

The **Best Buy App** must include the following components:  

| Service              | Description                                                                 | Notes                                      |
|----------------------|-----------------------------------------------------------------------------|--------------------------------------------|
| **Store-Front**      | Customer-facing app for browsing and placing orders.              |                                           |
| **Store-Admin**      | Employee-facing app for managing products and viewing orders .     |                                           |
| **Order-Service**    | Handles order creation and sends data to the managed order queue.          | Replace RabbitMQ with a managed service.  |
| **Product-Service**  | Handles CRUD operations for product data.                          |                                           |
| **Makeline-Service** | Processes and completes orders by reading from the order queue.       |                                           |
| **AI-Service**       | Generates product descriptions and images.                       | Use GPT-4 and DALL-E models.              |
| **Database**         | MongoDB for persisting order and product data.                            |                                           |

---

## **Project Requirements**  

### **1. Application Architecture**  
Design the application based on the provided diagram of Algonquin Pet Store(On Steroids).

### **2. Microservices Development**  
You can fork the Algonquin Pet Store repositories and use that as a starting point.

### **3. AI Integration**  
- Enable AI-generated product descriptions and images using GPT-4 and DALL-E models.  
- Use Azure OpenAI Services or OpenAI APIs for this integration.  

### **4. Kubernetes Deployment**  
- Use Kubernetes to deploy all services.  
- Create ConfigMaps and Secrets for managing application configurations and sensitive information.  
- Use StatefulSets for MongoDB.  
---

## **Assignment Deliverables**  

Your submission must include the following:

### **1. GitHub Repository**
The GitHub repository must include:  
1. A `README.md` file containing:  
   - **Updated Application Architecture**:  
     - Draw the updated architecture diagram using `Draw.io` and include it in the README.  
   - **Application and Architecture Explanation**:  
     - Briefly explain the application functionality and how the architecture works.  
   - **Deployment Instructions**:  
     - Step-by-step instructions to deploy the application in a Kubernetes cluster.  
   - **Table of Microservice Repositories**:  
     - A table listing each microservice repository and its GitHub link.  
     - Example:
       | **Service**         | **Repository Link**                       |
       |---------------------|-------------------------------------------|
       | Store-Front         | `<GitHub Link>`                           |
       | Order-Service       | `<GitHub Link>`                           |
   - **Table of Docker Images**:  
     - A table listing all Docker images you created, including their names and links to their Docker Hub repositories.  
     - Example:
       | **Service**         | **Docker Image Link**                     |
       |---------------------|-------------------------------------------|
       | Store-Front         | `<Docker Hub Link>`                       |
       | Order-Service       | `<Docker Hub Link>`                       |
    - **Any issues or limitations in the implementation (Optional)**

2. A **Deployment Files** subfolder:  
   - Include all Kubernetes deployment YAML files in a folder named `Deployment Files`.  
   - Ensure these files are clearly named (e.g., `store-front-deployment.yaml`, `order-service-deployment.yaml`).   

### **2. Demo Video**  
Record a **5-minute max demo video** showcasing the following:  
- The application in action after deployment to AKS cluster.  
- AI-generated product descriptions and images.  
- Integration with the managed order queue service.  

**Upload the video to YouTube** and include a link to the video in your `README.md` file under a "Demo Video" section.  

---

## **Grading Criteria**  

| **Criteria**                           | **Weight** |
|----------------------------------------|------------|
| Application Code and Documentation     | 20%        |
| Integration with Managed Order Queue   | 20%        |
| AI Integration (GPT-4 and DALL-E)      | 20%        |
| Kubernetes Deployment                  | 20%        |
| Demo Video                             | 20%        |

---

## **Resources**  
- **Algonquin Pet Store Repository:** [GitHub Link](https://github.com/ramymohamed10/algonquin-pet-store-on-steroids)  
---

## **Submission Instructions**  
1. Push your code and deployment files to your GitHub repository.  
2. Submit the GitHub repository link via Brightspace.  

--- 

### **Bonus Task: Implement a CI/CD Pipeline for Each Microservice (3 Bonus Marks)**  
Set up a **Continuous Integration/Continuous Deployment (CI/CD) pipeline** for all microservices to automate building, and deploying the application.

