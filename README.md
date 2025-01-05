## AWS_Lambda_CICD

This project automates the deployment of an AWS Lambda function using GitHub Actions, a tool that helps automate tasks like deploying code when changes are made. Here’s a breakdown of what it does:

### What is AWS Lambda?

AWS Lambda is a service provided by Amazon that allows you to run code (in this case, Python) without having to manage servers. You just upload your code, and Lambda takes care of running it.

### What is CI/CD?

CI/CD stands for Continuous Integration/Continuous Deployment. It’s a way to automatically test and deploy your code whenever you make changes. Instead of manually uploading new code, the process is automated to save time and reduce mistakes.

### How Does It Work?
	1.	GitHub Actions:
	•	Whenever someone pushes code to either the main or test branches, GitHub Actions automatically starts a process to deploy the Lambda function to AWS.
	2.	Lambda Function:
	•	The function makes a request to a fake API to get some data and displays the first few rows in a table (using a tool called Pandas).
	•	It also prints out environment variables (settings) like ENV (which can be prod or test), API_KEY (which is different for each environment), and LOG_LEVEL (how detailed the logs should be).
	3.	Environment Variables:
	•	The pipeline sets different environment variables based on whether the code is being deployed for testing (test) or for production (prod).
	4.	Deployment Process:
	•	The workflow packages the function, installs any required dependencies (like requests for making HTTP requests and pandas for processing data), and uploads it to AWS Lambda.
	•	If the Lambda function already exists, it updates the existing function with new code. If not, it creates a new Lambda function.

### How to Use
	1.	Set up AWS Credentials: You’ll need an AWS account with access to Lambda and a secret access key, which you store safely in GitHub.
	2.	Push Code: Whenever you make a change to the code and push it to GitHub (on the main or test branch), GitHub Actions will automatically take care of deploying the code to AWS.
	3.	See Results: The Lambda function will run automatically, retrieve some mock data, process it, and print out the results.

### Why This Is Useful

Instead of manually uploading your code every time, you set up this automation, which makes the whole process faster and reduces human errors. You can deploy code to AWS just by pushing it to a GitHub branch!
