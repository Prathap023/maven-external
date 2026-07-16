pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
       stage('build'){
            steps{
                bat ' mvn clean package'
            }
        }
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
    }
}