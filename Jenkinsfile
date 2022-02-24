pipeline {  
    agent any
   environment {
        // Using returnStdout
        CC = """${sh(
                returnStdout: true,
                script: 'echo "clang"'
            )}""" 
        // Using returnStatus
        EXIT_STATUS = """${sh(
                returnStatus: true,
                script: 'exit 1'
            )}"""
            }
    stages {        
        stage('Build') {
            steps {
                echo "Building...${env.BUILD_ID} on ${env.JENKINS_URL}.."                 
            }
        }
        
        stage('Test'){
            steps{
                echo 'Testing...'
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploying...'
            }
        }
    }
    
}
