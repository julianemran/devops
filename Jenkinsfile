pipeline {
    agent any
    /*parameters {
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'master', name: 'BRANCH', type: 'PT_BRANCH'
    }*/
    stages {
        stage('Checkout SCM') {
            steps {
                echo 'Clone the repo '
                sh 'git clone https://github.com/julianemran/devops.git'
            }
        }
        stage('Check what is new') {
            steps {
                sh 'cat devops/test_api.py'
            }
        }
        stage('Removing'){
            steps {
                sh 'rm -fr devops'
                echo 'Finished'
            }
        }
    }
}
