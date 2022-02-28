pipeline {  
    agent any
    environment{
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
        BITBUCKET_COMMON_CREDS = credentials('jenkins-bitbucket-common-creds')
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
                echo "credential AWS_ACCESS_KEY_ID is ${env.AWS_ACCESS_KEY_ID} "
                sh 'printenv'
                echo "test... ${env.CC}"
            }
        }
        
        stage('Test'){
            parameters {
                    string(name: 'STATEMENT', defaultValue: 'hello; ls /', description: 'What should I say?')
                }
            steps{                
                echo 'Testing...'
                sh("echo ${STATEMENT}")
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploying...'
            }
        }
    }
    
}
