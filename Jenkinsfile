pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Docker') {
            steps {
                bat 'docker build -t myapp .'
            }
        }

        stage('Run') {
            steps {
                bat 'docker run -d -p 8080:8080 myapp'
            }
        }
    }
}