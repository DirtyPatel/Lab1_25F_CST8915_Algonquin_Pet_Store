
## Submission

For this first lab, you will demonstrate both your ability to get the system running and your understanding of the individual services.

### What to Submit
1. **Demo Video (Max 5 minutes)**
   - Record a short demo video showing your running application.  
   - At minimum, your demo should include:
     - The application running on your Azure VM (store-front accessible in the browser).
     - A product listing being displayed from the Product Service.
     - An order being placed through the Order Service.
   - Upload your video to **YouTube** (unlisted is fine).
   - Copy the video link, you will include this in your `README.md` file.

2. **Brief Technical Explanation**
   - Spend some time examining the source code of each service:
     - **Order Service (Node.js)**
     - **Product Service (Rust)**
     - **Store Front (Vue.js)**
   - For each service, write a **short technical explanation** (1–2 paragraphs each):
     - What the service is responsible for.
     - Which language/framework it uses.
     - How it interacts with the other services (e.g., RabbitMQ, APIs, or front-end).
   - Keep it simple but show that you understand the role of each service.

3. **GitHub Repository**
   - Create a **GitHub repository** for your submission.
   - Your repository must include:
     - A `README.md` file with:
       - The YouTube video link.
       - Your written technical explanations for the three services.
     - (Optional) Any notes you want to share about setup challenges or learnings.

### How to Submit
- Push your work to a public GitHub repository.
- Include the YouTube demo link and explanations in the `README.md`.
- Submit the link to your GitHub repository as your final lab deliverable in **Brightspace**.


# SUBMISSION
- CST8915 – Lab 1: Algonquin Pet Store
- The lab demonstrated deploying and running a microservice based application on Azure VM

- The system is made up of multiple services: 
  - Store-Front (Vue.js)- The frontend web interface that customers use
  - Product-Service (Rust)- Manages product catalog and prices
  - Order-Service(Node.js)- Process customer orders
  - RabbitMQ(Message Broker)- Allows asynchronous, reliable communication between service


## Youtube Link

-https://youtu.be/gYJ0dnXC4Sk

## Store-Front
  - Built using Vue.js
  - This is customer facing web app, provides interface where customers can browse, calculate totals, and place oorders
  - Doesnt store data itself but instead fetches from product services and sends orders to Order service

## Product-Service
  - Its written in Rust, and chosen for speen and safety
  - Responsible for managing the product catalog ( names, prices)
  - Store front uses Product services endpoint to show products to customers
  
## Order-Service
  - Built with Node.js
  - Accepts orders from the store-Front and sends them to RabbitMQ
  - RabbitMQ queues the orders so they dont lost when the system gets busy
  - The main job is to process orders reliably and not process everything itself

 ## RabbitMQ
  - It takes messages and makes sure they get delivered safely
  - The Order service drops new orders into RabbitMQ instead of sending them somewhere else
  - so the orders dont get lost if another service is busy they just wait in queue untill processed
  - it keeps the services loosely connected so each one an do its job without depending on the others speed.
  
