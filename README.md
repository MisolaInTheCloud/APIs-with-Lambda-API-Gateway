<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# APIs with Lambda + API Gateway

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-compute-api)

**Author:** Kemisola Adelakun | MisolaInTheCloud  
**Email:** misolakhemmy@gmail.com

---

![Image](http://learn.nextwork.org/curious_olive_fierce_frog/uploads/aws-compute-api_c9d0e1f2)

---

## Introducing Today's Project!

In this project, I will demonstrate how to build and deploy the logic tier of a three-tier web application using AWS Lambda and API Gateway. 

I'm doing this project to learn how to create serverless functions that respond to user requests, handle backend logic, and integrate seamlessly with other AWS services. 

This is the brain of the application, the part that takes user actions and converts them into actual features, such as retrieving data or triggering workflows. It’s all about scalable, event-driven architecture, and I’m excited to get hands-on with it!

### Tools and concepts

Services I used were AWS Lambda ND Amazon API Gateway. Key concepts I learnt include Lambda functions, which allow me to run code without provisioning servers, and API Gateway, which acts as a front door for HTTP requests to access backend services. I also explored proxy integration, RESTful API design, creating resources and methods, and deploying APIs to different stages, like prod. This project gave me a solid understanding of building and exposing serverless backend logic in a secure and scalable way.

### Project reflection

This project took me approximately 1 hour to complete. The most challenging part was understanding how Lambda proxy integration works and making sure the API methods were correctly linked to my Lambda function. 

It was most rewarding to successfully deploy the API and see it respond through the public endpoint, knowing I had just built a working serverless backend from scratch!


I did this project today because I wanted to build hands-on experience with serverless architecture, especially using Lambda and API Gateway, which are crucial tools for modern cloud development. I’ve been focusing on strengthening my backend skills and understanding how different AWS services connect in real-world use cases. This project met my goals, it helped me understand how to expose backend logic through an API, handle requests securely, and document everything using OpenAPI standards

---

## Lambda functions

AWS Lambda is a serverless compute service that lets you run code without provisioning or managing servers. I'm using Lambda in this project to handle the backend logic of my application, specifically, to process requests and retrieve user data. Lambda allows me to write and deploy functions that automatically run in response to events (like an API call), making it perfect for building lightweight, scalable backend services in a three-tier architecture.

The code I added to my function will retrieve user data from a DynamoDB table based on a provided userId. It queries the table, checks if the user exists, and then returns the corresponding data in a JSON response. If the userId is not found or if something goes wrong during the lookup, the function returns an error message instead. This simulates how a backend service would handle user-specific data requests in a real application.

![Image](http://learn.nextwork.org/curious_olive_fierce_frog/uploads/aws-compute-api_a1b2c3d5)

---

## API Gateway

APIs are Application Programming Interfaces; they allow different software systems to communicate with each other. There are different types of APIs, like REST APIs (which use standard HTTP methods), GraphQL APIs (which allow more flexible queries), and WebSocket APIs (for real-time communication). 

My API is a REST API built with Amazon API Gateway, and it acts as the front door to my Lambda function, enabling users to interact with my backend logic through simple HTTP requests like GET or POST.

Amazon API Gateway is a fully managed service that makes it easy to create, publish, and manage APIs at any scale. I'm using API Gateway in this project to create a RESTful API that connects the frontend of my application to the backend Lambda function. It allows users to send HTTP requests (like GET or POST), which are then routed to the Lambda function to process and return data, forming the logic layer of my three-tier architecture.

When a user makes a request, like clicking a button or loading a page, API Gateway receives that request and passes it to the connected Lambda function. Lambda then processes the request, runs the necessary backend logic (like retrieving data from a database), and sends the response back through API Gateway to the user’s browser. This seamless interaction allows the frontend to communicate with serverless backend logic, making the app scalable, responsive, and cost-efficient.

![Image](http://learn.nextwork.org/curious_olive_fierce_frog/uploads/aws-compute-api_m3n4o5p6)

---

## API Resources and Methods

An API is made up of resources, which are specific endpoints that represent different parts of the application's functionality. Each resource typically corresponds to a noun, like /users, /products, or /orders, and can support various HTTP methods like GET, POST, PUT, or DELETE. Resources help organize the API into logical sections, making it easier to manage, scale, and interact with, just like how different pages or features exist in a web application.

Each resource consists of methods, which are actions that define how clients can interact with that specific part of the API. These methods are based on standard HTTP commands, like GET (to retrieve data), POST (to create data), PUT (to update data), and DELETE (to remove data). By assigning methods to resources, I control what kind of operations can be performed, making my API functional and interactive.






I created a GET method for the /users resource and enabled Lambda proxy integration. This means that when someone sends a GET request to this endpoint, the full request is passed directly to the Lambda function, allowing it to access headers, query parameters, and other request details just like a real backend would in a production environment.

![Image](http://learn.nextwork.org/curious_olive_fierce_frog/uploads/aws-compute-api_c9d0e1f2)

---

## API Deployment

When I deploy an API, I deploy it to a specific stage. A stage is a versioned environment, like development, testing, or production, that helps me control which version of the API is live and who can access it. I deployed to the prod (production) stage because I’m ready for this version to go live and be accessible through a public endpoint. 

To visit my API, I opened the Invoke URL from the prod stage of my API Gateway setup. This URL is the live endpoint that users or applications would use to access my backend logic. The API displayed an error because I haven’t created or connected the DynamoDB table yet, so the Lambda function couldn’t retrieve any data.

That’s totally expected, my serverless API setup is complete, and I’m all set for the next step: connecting the data layer!




![Image](http://learn.nextwork.org/curious_olive_fierce_frog/uploads/aws-compute-api_3ethryj2)

---

## API Documentation

For my project's extension, I am writing API documentation because it helps explain how my API works, what endpoints exist, what methods they support, what parameters are required, and what kind of responses to expect. This is especially useful for developers who might want to use or build on my API in the future. 

Once I have prepared my documentation, I can publish it to the prod stage of my API so it matches the live version that users will interact with. You have to publish your API to a specific stage because each stage (like dev, test, or prod) might have different versions or configurations of your API. This ensures that the documentation is accurate and relevant to the exact version that’s deployed, helping developers understand and interact with the correct functionality.

My published and downloaded documentation showed me a structured overview of my API, including the base path, available resources like /users, the HTTP methods (e.g. GET), and details like request parameters, response formats, and status codes. It also included metadata such as the API title, version, and descriptions I added. This documentation acts like a blueprint for how my API works, perfect for other developers or tools like Swagger UI to visualise and interact with my endpoints.










![Image](http://learn.nextwork.org/curious_olive_fierce_frog/uploads/aws-compute-api_z9a0b1c2)

---

---
