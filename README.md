# Cloud-Resume-Challenge
The [Cloud Resume Challenge](https://cloudresumechallenge.dev/docs/the-challenge/aws/) is a project created by [Forrest Brazeal](https://forrestbrazeal.com/) to showcase the various skills used by DevOps Engineers and Cloud Developers. Its focus is on encouraging self-learning by providing a basic understanding of key topics such as APIs, Testing, IaC, and CI/CD pipelines.

The website was built using popular AWS technologies like S3, CloudFront, Certificate Manager, Lambda, DynamoDB, API Gateway, and the Boto3 Python SDK.

The Infrastructure-as-Code is managed using SAM and the CI/CD pipeline is run using GitHub Actions.

<img src="https://github.com/BerkayTuran/Cloud-Resume-Challenge/blob/main/Cloud-Resume-Challenge.jpg" alt="Website Architecture Diagram">

## Steps:

- [x]  1. Write Resume in **HTML & CSS**
    - A template was created with HTML and CSS.

- [x]  2. Creating the deployment with **AWS SAM**
    - SAM CLI for SAM is installed and keys are assigned.
    - The distribution was created after granting permissions from the IAM service.

- [x]  3. Deploy Static Website with  **AWS S3**
    - S3 was created with template.yaml template.
    - Added 'PublicRead' property and 'index.html' file to SAM template.

- [x]  4. Use HTTPS Protocol with **AWS CloudFront**
    - Redirect any HTTP requests to HTTPS
    - Verified SSL certificate

- [x]  5. Point Custom DNS Domain Name with **AWS CloudFront**
    - A subdomain has been created on the previously owned domain.
    - Created 'CNAME value' and 'CNAME name' request for DNS validation.
    - A record has been created from the subdomain panel and the subdomain has been connected.

- [x]  6. Create a Webpage Visitor Counter with **Javascript**
    - POST request sent to Lambda funcion using Fetch API
    - Latest number of page views displayed to visitor at page bottom

- [x]  7. Create a Visitor Counter Database with **AWS DynamoDB**
    - Created DynamoDB with AWS SAM CLI.
    - NoSQL database holds single record with single attribute which is updated by Lambda function

- [x]  8. Connect Webpage to Database with **AWS API Gateway + Lambda**
    - REST API exposes URL endpoint, allowing for GET and POST requests
    - API call invokes Lambda function, relaying function return value as API response to website

- [x] 9. Write a Lambda Function with **Python + AWS Boto3 SDK**
    - Boto3 SDK manages DynamoDB table, retrieving and updating value of view count record
    - Function checks latest count from table, increments +1, and persists new value back to table
    - Function returns JSON response to API, to deliver JSON resposne back to website

- [x] 10. Perform **Tests** on Python Code
    - Tests run on 'unittest' framework, with lambda function imported locally to be tested

- [x] 11. Utilize **Source Control** with GitHub
    - All code related to website stored in a GitHub repository
    - Version control utilized to track changes and capture development over time
    - `.gitignore` file used to avoid committing binary / superfluous files (e.g. .terraform and pycache directories) to remote repo

- [x] 12. Implement **Backend and Frontend CI/CD** with GitHub Actions
    - Workflow runs on GitHub-hosted Linux runner
    - Keys are assigned to New Secrets from the Secrets menu.
    - After the tests run successfully, the IaC changes are submitted, then the changes from the website.
    - Unit tests run on new Lambda code, then AWS SAM changes applied, and finally integration test run on API endpoint