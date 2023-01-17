pipeline {
  agent any
     environment {
        AWS_REGION  = 'us-east-1'
    }
stages {

    stage('docker build and push to ecr') {
      
      steps {

       sh(label: 'ECR login and docker push', script:
         '''
         #!/bin/bash
         
           echo "Authenticate with ECR"
            set +x # Don't echo credentials from the login command!
            echo "Building New ECR Image"
            eval $(aws ecr get-login --region "$AWS_REGION" --no-include-email)
            # Enable Debug and Exit immediately 
            set -xe
            docker build -t nano .
            #two push one for master tag other is git commit ID
            docker tag nano:latest 839641684748.dkr.ecr.us-east-1.amazonaws.com/nano:latest
            docker push 839641684748.dkr.ecr.us-east-1.amazonaws.com/nano:latest
         '''.stripIndent())
      }
    }
}
