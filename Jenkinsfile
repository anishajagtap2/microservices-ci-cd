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
                //bat 'py -m unittest'
                bat '"C:\\Users\\DDR\\AppData\\Local\\Programs\\Python\\Python314\\python.exe" -m unittest'
            }
        }
<<<<<<< HEAD
        stage('Push') {
            steps {
                 sh 'docker build -t anishajagtap2/my-app:$8 .'
                sh 'docker push anishajagtap2/my-app:$8'
    }
}
=======
>>>>>>> d281069cc81111fe5425b1d7bd5d105f70852724
    }
}
