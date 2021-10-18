- ### Backend Architecture

  - ### Overview of Back End

    The backend consists of two resources:
    - /StoreAndNotify - a POST for submitting the feedback, storing the data in DynamoDB and then triggering a notification.
    - /PublishorDelete - a POST method for publishing the feedback if it's approved, or deleting the feedback if it's not approved.

  - ### Feedback Submission
    A feedback submitted from the front end will trigger the /StoreAndNotify api which in turn triggers the AWS Step Fucntion. This step function will orchestrate the lambda functions created to process the storage of the feedback. The two lambdas for processing the submit functionality are
      - /StoreComment - store the comment in DynamoDB
      - /Notify - the success of the previous function will invoke the notification and is then sent out to the admin for adminnistration.

  - ### Feedback Governance
    When the feedback is stored in the DynamoDB, the second step function is invoked which notifies the admin via an email that a submissions is ready for approval. There are two lambdas in this step function:
    - /DeleteComment - In case the feedback is not in line with community guidelines, or contains profanity etc., the admin has the choice to delete the feedback and notify the user about violating community guidelines.
    - /ApproveComment - in case the feedback does not violate community guidelines, the admin can approve the feedback and the lambda will create a secondary index in DynamoDB with the approved_feedback attribute set as 1.

 - ### Technology Stack Used in the Back End + Business Layer
   - Lambda - Node.js 14.x/Python 3.6
   - Step Function -  ASL, Amazon States Language JSON formatted Step Function code
   - DynamoDB - Python
