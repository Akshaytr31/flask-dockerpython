pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build --tag python-docker .' 
            }
        }
    }
}
