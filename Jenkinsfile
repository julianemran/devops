pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'some changes'
            }
        }
        stage('Test') {
            steps {
                echo 'Test completed'
                sh 'date'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy completed'
            }
        }
        stage('Github') {
            steps {
                echo 'Hello from github'
            }
        }
    }
}
