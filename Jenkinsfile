pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'docker build -t my-app .'
            }
        }

        stage('Test') {
            steps {
                bat 'py -m unittest'
            }
        }
    }
}