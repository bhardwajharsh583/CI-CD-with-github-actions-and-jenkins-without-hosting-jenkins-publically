# CI/CD with github-actions and jenkins without hosting jenkins publically
This project shows how to create a complete pipeline that triggers jenkins build whenever a PR is created. The fun part is that unlike any other hosted jenkins server we will use github actions runner to host an on-premise jenkins server.

## Github Actions
  - Used github actions to trigger a pipeline whenever a PR is raised
  - Github actions include various steps and is also responsible for triggering our jenkins build remotely
  - Used the github api inside github actions to send back build status and reflect jenkins build status in PR

    ![github-actions-workflow-pipeline](https://github.com/bhardwajharsh583/CI-CD-with-github-actions-and-jenkins-without-hosting-jenkins-publically/assets/69351159/da7aab6f-8b58-430b-8d26-08dc5aef7475)
    (Github actions pipeline)
 
## Using the Self-Hosted Runner
  - By default github actions creates a container to execute the steps but that requires our jenkins to be publically hosted therefore used self-hosted actions-runner.
  - To connect local jenkins server with github, used the self-hosted github runner that we can create in our system and run (as a service as well)
  - We can check runner logs in our system through CLI
  - NOTE: we have to add our jenkins url as http://LOCAL_IP:8080 in github secrets along with other secrets required in workflows .yml file

  ![github-actions-runner-terminal](https://github.com/bhardwajharsh583/CI-CD-with-github-actions-and-jenkins-without-hosting-jenkins-publically/assets/69351159/1f380c37-90a8-49be-86b8-49de1037e08b)
  (Runner logs)
  
## PR status and Build results
  Used github API  to send back results of your pipeline and jenkins build and reflect the same on PR

  ![github-pr-status-2](https://github.com/bhardwajharsh583/CI-CD-with-github-actions-and-jenkins-without-hosting-jenkins-publically/assets/69351159/bfeb656d-8fc9-46d7-90d3-5615253971f1)
  (PR status)
  
  ![image](https://github.com/bhardwajharsh583/CI-CD-with-github-actions-and-jenkins-without-hosting-jenkins-publically/assets/69351159/56c687fa-4546-4628-8eed-da8a602e44a1)
  (Build Status in PR)
