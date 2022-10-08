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
                sh 'kubectl apply -f deploymentservice.yml' kubeconfigid:| '5fcb4580-e2bb-47aa-96bc-16466402fc92'
	    }
	}
    }
}
			    
                
	
    

