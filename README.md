# Go-AWS-Lambda-Tutorial
This is the basic tutorial to showcase the deployment  of  Go Code on AWS Lambda function via CLI

Steps to create and Invoke Lambda functions via CLI

# Step 1- Install AWS CLI on computer(Mine is Linux based)
        
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

# Step 2- Run the configuration command

aws --version
aws configure 

Enter Access Token, Access Secret Token genereated while creating User in IAM roles via Aws console

# Step 3- Build the main.go file

Execute command go build main.go. This will create a main executable 

# Step 4- Create a Zip file of the main executable

Execute command zip function.zip main

# Step 5- Create lambda function 

aws lambda create-function --function-name go-lambda-function \
--zip-file fileb://function.zip --handler main --runtime go1.x \
--role arn:aws:iam::<YOUR USER IAM ID>:role/lambda-ex
 
# Step 6- Invoke the lambda function 
  
aws lambda invoke --function-name go-lambda-function --cli-binary-format raw-in-base64-out --payload '{"What is your name?": "Ashutosh","How old are you?":33}' output.txt
  
This will write a text file output.txt with the reponse.
  
  
  
# ENJOYYYYY!!!!!
  




