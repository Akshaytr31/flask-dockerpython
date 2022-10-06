pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build --tag python-docker .' 
                git credentialsId: '7f5b8167-32d8-47ad-abd5-08f095e5a4d0', url: 'https://github.com/Akshaytr31/flask-dockerpython.git'
            }
        }
    }
}
