pipeline {
    agent any
	
    environment {
        DOCKERHUB_CREDENTIALS = credentials('7b81671e-bd25-40fb-aa2b-b001a0226648')
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker build --tag akshaytr123/flask-dockerpython .'
            }
        }
        stage('Login to dockerhub') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage('push image') {
            steps {
                sh 'docker push akshaytr123/flask-dockerpython'
            }
        }
	stage('Deploying the appto kubernetes') {
            steps {
                script {
                    kubernetesDeploy(configs: "deployment.yml", kubeconfigid:| "c3783aed-5a5a-4eb6-a718-0098991b5471")
                }
            }
	}
    }
}
	
    

