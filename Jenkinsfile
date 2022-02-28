pipeline {  
    agent any
    environment{
        CC="""${sh(
            returnStdout: true,
            script: 'echo "clang"'
        )}"""
        EXIT_STATUS="""${sh(
            returnStatus: true,
            script: 'exit 1'
        )}"""
        AWS_ACCESS_KEY_ID=credentials('jenkins-aws-secret-key-id')
	AWS_SECRET_ACCESS_KEY=credentials('jenkins-aws-secret-access-key')
    }
    stages {        
        stage('Build') {
            environment {
                DEBUG_FLAGS = '-g'
            }
            steps {
                echo "Building...${env.BUILD_ID} on ${env.JENKINS_URL}.."  
                
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
