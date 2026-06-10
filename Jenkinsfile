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

stage('Package') {
    steps {
        writeFile file: 'artifact.txt', text: "Build number: ${env.BUILD_NUMBER}"
        archiveArtifacts artifacts: 'artifact.txt'
    }
}