The main idea is to trigger a CD workflow on pull requests , the workflow will build the app into docker image, push it to dockerhub , which will be later pulled by the deployment stage and deployed to the EKS cluster :

![Capture d'écran 2024-09-04 202634](https://github.com/user-attachments/assets/3e0fb331-13b0-4a1d-83ea-6ab6039d2a36)

We will use Docker Buildx to build the image :

![Capture d'écran 2024-09-04 204055](https://github.com/user-attachments/assets/4d98f5a8-b67e-4e26-9f40-e8acf81c5258)

Note : i used this documentation for the "Login to Dockerhub" and "configure AWS Credentials" steps : 

https://github.com/docker/build-push-action

https://github.com/aws-actions/configure-aws-credentials

Next Step is to create docker secrets and aws secrets in the repo :

![Capture d'écran 2024-09-04 203044](https://github.com/user-attachments/assets/f3bcba46-657e-46e8-8512-13e7fefb1c80)

Then checkout to another branch and simply modify readme.md and push again so the CD workflow is triggered :

![Capture d'écran 2024-09-04 203458](https://github.com/user-attachments/assets/c3ca2dfe-fa6f-4d4f-9ade-5a5456a5aa2a)

*build and push to dockerhub after successfully login in*

![Capture d'écran 2024-09-04 203527](https://github.com/user-attachments/assets/78f20516-308a-4a21-a727-b8f8f03eb986)

*configuring AWS credentials*

![Capture d'écran 2024-09-04 203537](https://github.com/user-attachments/assets/2a95c0c0-79de-47e9-bffc-31000da18eed)

*succefully deploying the app on EKS with the deployment file*

![Capture d'écran 2024-09-04 203559](https://github.com/user-attachments/assets/e99746ff-cf58-4097-a5f5-850d33b0be35)

END

https://github.com/docker/build-push-action
https://github.com/aws-actions/configure-aws-credentials
