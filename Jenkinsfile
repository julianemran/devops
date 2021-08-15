pipeline {
    agent any
    /*parameters {
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'master', name: 'BRANCH', type: 'PT_BRANCH'
    }*/
    stages {
        stage('Checkout SCM') {
            steps {
                git branch: 'main', url: 'https://github.com/julianemran/devops.git'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t fastapiimage .'
                echo 'Build completed'
            }
        }
        stage('Run') {
            steps {
                sh 'docker run -d --name fastapicont -p 8000:80 fastapiimage'
                echo 'Run completed'
            }
        }
        stage('Test') {
            steps {
                echo "----------------------------"
                sh 'pytest test_api.py -v'
                echo 'Testing completed'
                echo "----------------------------"
            }
        }
        stage('Stop and Removing'){
            steps {
                sh 'docker stop fastapicont'
                sh 'docker rm fastapicont'
                sh 'docker rmi fastapicont'
                echo 'Finished'
            }
        }
    }
}
