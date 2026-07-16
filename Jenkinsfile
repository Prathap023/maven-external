pipeline{
    agent any
    stages{
        stage('checkout'){
            steps{
                checkout scm
            }
        }
        stage('build'){
            steps{
                bat 'mvn clean package'
            }
        }
        stage('docker'){
            steps{
                bat 'docker build -d maven-external'
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