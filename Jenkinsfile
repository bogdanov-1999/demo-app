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
                echo 'Запускаем тесты'
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