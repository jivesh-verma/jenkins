
pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages{
        stage('Build and tag image') {
            steps {
                sh 'docker build -t nano .'
            }
        }  
    }
}
