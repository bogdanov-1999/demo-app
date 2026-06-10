pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Получаем код из GitHub'
            }
        }

        stage('Build') {
            steps {
                echo 'Собираем приложение'
            }
        }

        stage('Test') {
            steps {
                bat 'findstr "Hello Jenkins" app.txt'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t demo-app:%BUILD_NUMBER% .'
            }
        }

        stage('Run Container') {
            steps {
                 bat "docker run --rm demo-app:${env.BUILD_NUMBER}"
            }
        }

        stage('Package') {
            steps {
                writeFile file: 'artifact.txt', text: "Build number: ${env.BUILD_NUMBER}"
                archiveArtifacts artifacts: 'artifact.txt'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Развертывание завершено'
            }
        }
    }
}

