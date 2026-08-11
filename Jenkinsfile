pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t my-cicd-app:latest .'
            }
        }

        stage('Docker Run Test') {
            steps {
                sh 'docker run --rm my-cicd-app:latest'
            }
        }
    }
}
