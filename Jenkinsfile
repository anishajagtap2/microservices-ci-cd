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
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'docker build -t anisha1099/my-app:%BUILD_NUMBER% .'
            }
        }

        // stage('Build') {
        //     steps {
        //         bat 'docker build -t my-app .'
        //     }
        // }

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

        stage('Deploy') {
            steps {
                bat '''
                kubectl set image deployment/my-app \
                my-app=anisha1099/my-app:$BUILD_NUMBER
                '''
            }
        }


        try {
            sh 'kubectl apply -f deployment.yaml'
        }
        catch(Exception e) {
            sh 'kubectl rollout undo deployment/my-app'
        }
    }
}