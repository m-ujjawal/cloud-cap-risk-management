pipeline {  
    agent any
    stages {        
        stage('Build') {
            steps {
                echo "Building...${env.BUILD_ID} on ${env.JENKINS_URL}.." 
                sh 'make' 
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
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
