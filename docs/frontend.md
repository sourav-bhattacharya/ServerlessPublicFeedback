- ### Frontend Architecture
  - ### Overview of Front End
  
    The front end is built using React, on AWS Amplify to simplify front end management. When a developer commits code to CodeCommit, AWS Amplify will trigger the inbuilt CI/CD pipeline to deploy the change to the application. The developer can store the settings in the amplify.yml file. Amplify will also provide CDN, password protection, cache invalidation, redirection services etc., without the need to manage any EC2 instances or setup additional services for front end management.
    
  - ### How to Invoke the Backend using API Gateway
  
    To invoke the backend of the application, the user will enter the feedback in the front end and click submit. The backend consists of two separate APIs: StoreAndNotify and PublishOrDelete. The first API, StoreAndNotify, is invoked when the user submits the feedback. A simple JS file can be used to validate the input and display success or failure message to the end user, followed by reseting the fields. User can also be allowed to submit the feedback anonymously, if they choose to do so.

