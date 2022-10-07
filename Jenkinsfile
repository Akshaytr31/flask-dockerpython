pipeline {
    agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('3e2c32bc-08f1-462f-a571-bb8999b2394e')
	}
    stages {
        stage('Build') {
            steps {
                sh 'docker build --tag akshaytr123/flask-dockerpython .'
            }
        }
	stage('Login') {

	steps {
		sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
	     }
	}
        stage('push') {
            steps {
                sh 'docker push akshaytr123/flask-dockerpython:1.1'
            }          
        }
    }
}
