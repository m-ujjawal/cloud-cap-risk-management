pipeline {  
    agent any
    environment{
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        
        CC="""${sh(
            returnStdout: true,
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
                echo "test... ${env.CC}"
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
