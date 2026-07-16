pipeline{
    agent any
    stages{
        stage('checkout'){
            scm checkout
        }
        stage('build'){
            bat 'docker build -d maven-external'
        }
        stage('run'){
            bat 'docker run -p 8081:8081 maven-external'
        }
        stage('test'){
            bat 'curl http://localhost:8081'
        }
    }
}