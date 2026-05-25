// pipeline {
//     agent any

//     stages {

//         stage('Clone') {
//             steps {
//                 checkout scm
//             }
//         }

//         stage('Build') {
//             steps {
//                 bat 'docker build -t my-app .'
//             }
//         }

//         stage('Test') {
//             steps {
//                 //bat 'py -m unittest'
//                 bat '"C:\\Users\\DDR\\AppData\\Local\\Programs\\Python\\Python314\\python.exe" -m unittest'
//             }
//         }
//     //     stage('Push') {
//     //         steps {
//     //             bat 'docker build -t anishajagtap2/my-app:%8% .'
//     //             bat 'docker push anishajagtap2/my-app:%8%'
//     // }

//         stage('Push') {
//             steps {
//                 bat 'docker build -t anishajagtap2/my-app:%BUILD_NUMBER% .'
//                 bat 'docker push anishajagtap2/my-app:%BUILD_NUMBER%'
//             }
//         }
//     }
// }

pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/anishajagtap2/microservices-ci-cd.git'
            }
        }

        stage('Build') {
            steps {
                bat 'docker build -t anisha1099/my-app:%BUILD_NUMBER% .'
            }
        }

        stage('Test') {
            steps {
                bat '"C:\\Users\\DDR\\AppData\\Local\\Programs\\Python\\Python314\\python.exe" -m unittest'
            }
        }

        stage('Push') {
            steps {
                bat 'docker push anisha1099/my-app:%BUILD_NUMBER%'
            }
        }
    }
}