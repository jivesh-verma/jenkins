
pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages{
        stage('Build and tag image') {
            steps {
                sh 'docker build -t nano Dockerfile '
                sh 'docker tag nano:latest 839641684748.dkr.ecr.us-east-1.amazonaws.com/nano:latest'
            }
        }  
    }
}
