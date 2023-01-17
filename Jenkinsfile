
pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
        stage('Build and tag image') {
            steps {
                sh 'docker build -t nano .'
                sh 'docker tag nano:latest 839641684748.dkr.ecr.us-east-1.amazonaws.com/nano:latest'
            }
        }           
}
