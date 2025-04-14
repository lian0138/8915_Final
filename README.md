-   **Updated Application Architecture**:
    -   Draw the updated architecture diagram using  `Draw.io`  and include it in the README.
![enter image description here](https://github.com/lian0138/8915_Final/blob/main/img/diagram.png?raw=true)

-   **Application and Architecture Explanation**:
    -   Briefly explain the application functionality and how the architecture works.

The Algonquin BustBuy project is a reimagined e-commerce platform where customers and staff interact through a streamlined architecture. The store-front, built with Vue.js, allows customers to place orders, which are handled by the order-service (Javascript) and sent via Azure Service Bus to the makeline-service (Golang) for processing and completion. Staff use the admin-front, also in Vue.js, to manage products and monitor order queues, interacting with the product-service (Rust) for CRUD operations on products. The makeline-service stores order data in a MongoDB database, ensuring persistence, while the optional ai-service (Python) can generate text and graphics to enhance the platform. The services communicate efficiently through Azure Service Bus, replacing RabbitMQ.

-   **Deployment Instructions**:
    -   Step-by-step instructions to deploy the application in a Kubernetes cluster.
 1. Build a resource group and Azure Kubernetes cluster with enough resources.
 ![enter image description here](https://github.com/lian0138/8915_Final/blob/main/img/Report_001.png?raw=true)
 ![enter image description here](https://github.com/lian0138/8915_Final/blob/main/img/Report_002.png?raw=true)
Get the subscription ID here
 2. Use Azure CLI to connect to the Azure subscription ID. (Linux)
![enter image description here](https://github.com/lian0138/8915_Final/blob/main/img/Report_004.png?raw=true)
 4. Build a namespace for this project with the command below.
```
kubectl create namespace 8915final
```
 6. Apply the yaml files as the command below
 ![enter image description here](https://github.com/lian0138/8915_Final/blob/main/img/Report_005.png?raw=true)
```
kubectl apply -f config-maps.yaml
kubectl apply -f secrets.yaml
kubectl apply -f aio.yaml
```

-   **Table of Microservice Repositories**:
    -   A table listing each microservice repository and its GitHub link
        
        Store-Front
        https://github.com/lian0138/storeFront_8915final
        Store-Admin
        https://github.com/lian0138/storeAdmin_8915final
        Order-Service
        https://github.com/lian0138/orderService_8915final
        Product-Service
        https://github.com/lian0138/productService_8915final
        Makeline-Service
        https://github.com/lian0138/makeLine_8915final
        AI-Service
        https://github.com/lian0138/aiService_8915final

-   **Table of Docker Images**:
    -   A table listing all the Docker images you created, including their names and links to their Docker Hub repositories
        
        Store-Front: 
        * chrisxuleung/store-front:8915final
        https://hub.docker.com/repository/docker/chrisxuleung/store-front/tags/8915final/sha256-a269478596e04baf83aa940e832c52040f85abab899ff2128f84dd3a429814f9
        Store-Admin: 
        * chrisxuleung/store-admin:8915final
        https://hub.docker.com/repository/docker/chrisxuleung/store-admin/tags/8915final/sha256-839bc2c81ee9610ed4fcc18b58ffbc85baf03a2f1ca733f85a89f3200be6c85c
        Order-Service: 
        * chrisxuleung/order-service:8915final
        https://hub.docker.com/repository/docker/chrisxuleung/order-service/tags/8915final/sha256-b3e0b6d9cf54e8894775f68c8b3d7b4aa53a0f98e4e7e8d6b50c10b5dbfa8f59
        Product-Service: 
        * chrisxuleung/product-service:8915final
        https://hub.docker.com/repository/docker/chrisxuleung/product-service/tags/8915final/sha256-b0f2f8c8c96685272eee1d00b8c45aa032982b95b438ef7c7af642706203c390
        Makeline-Service: 
        * chrisxuleung/makeline-service:8915final
        https://hub.docker.com/repository/docker/chrisxuleung/makeline-service/tags/8915final/sha256-6d8d75e18b2eff4e029311f489f3558fbea337bb58d1f4c89635fcc7f0f6fe00
        AI-Service: 
        * chrisxuleung/ai-service:8915final
        https://hub.docker.com/repository/docker/chrisxuleung/ai-service/tags/8915final/sha256-a90952ffe0d6ec3ed1a1ba983e61be8c7d64d2a594a528a212508bc5679e66de
        
-   **Any issues or limitations in the implementation (Optional)**
1. Azure AI-Service cannot be connect
2. The CI_CD script is without namespace, so I modified it to support namespace because I made a namespace as 8915final in this project.