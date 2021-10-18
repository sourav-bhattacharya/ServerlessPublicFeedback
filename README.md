# ServerlessPublicFeedbackApp
Public facing feedback submission solution 3 tier application: Presentation, business logic, storage. Which tech would you use for each stack, including programming language Using only serverless technologies. In AWS.

This repo aims to provide documentation on the Serverless Feedback Application. The application receives feedback in the form of comments via a front end hosted on React, which is then submitted into DynamoDB and a notification is triggered to the admin. The admin has the option to either approve or delete the comment. The OP is then notified of the status of the comment.

## Architecture

### High-level architecture
