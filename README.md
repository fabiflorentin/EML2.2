# EML2.2
Github Action example to update AWS lambda code using AWS ECR image .

## Architecture:
![image](https://github.com/user-attachments/assets/3cec3672-5c71-4f03-a042-ae47f5a06ebf)

## Pipeline:

![image](https://github.com/user-attachments/assets/0727fcf7-e4b5-49f9-a3bf-b1eb2e1ae0dd)

### Steps:
* Once code is committed to main branch, the pipeline is started;
* Using the AWS secrets stored at github actions secrets, the pipeline downloads the model from S3;
* Build the code for DetectPlate and store it to AWS ECR;
* After, the AWS lambda is updated to use the new image that has just built and stored at ECR.

