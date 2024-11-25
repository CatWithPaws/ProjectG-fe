pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                echo 'Building...'
                sh 'npm install' 
            }
        }
        stage('Test'){
            steps{
                echo 'Testing'
                sh 'npm test'
            }
        }
        stage ('Deploying'){
            environment{
                url = credentials('Jenkins-ProjectG-CD-TriggerUrl')
            }
            steps{
                echo 'Sending deploy command to prod server'
                sh 'curl -X POST "$url"'
            }
        }
    }
}

