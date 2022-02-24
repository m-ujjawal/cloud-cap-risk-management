pipeline {  
    agent any
    environment{
        CC="""${sh(
            returnStdout: false,
            script: 'echo "clang"'
        )}"""
        EXIT_STATUS="""${sh(
            returnStatus: true,
            script: 'exit 1'
        )}"""
    }
    stages {        
        stage('Build') {
            environment {
                DEBUG_FLAGS = '-g'
            }
            steps {
                echo "Building...${env.BUILD_ID} on ${env.JENKINS_URL}.."  
                sh 'printenv'
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
