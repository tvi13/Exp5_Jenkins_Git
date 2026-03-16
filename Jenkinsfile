pipeline {
    agent any
    stages {
        stage('Pull from Git') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'python3 -m py_compile build_check.py'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'python3 build_check.py'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'mkdir -p deploy && cp build_check.py deploy/'
            }
        }
    }
}
