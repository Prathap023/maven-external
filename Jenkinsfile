pipeline{
    agent any
    stages{
       
        stage('docker'){
            steps{
                bat 'docker build -t maven-external .'
            }
        }
        stage('run'){
            steps{
                bat 'docker run -p 8081:8081 maven-external'
            }
        }
        stage('test'){
            steps{
                bat 'curl http://localhost:8081'
            }
        }
    }
}